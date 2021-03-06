[![Build Status](https://travis-ci.org/rosette-api/R.svg?branch=master)](https://travis-ci.org/rosette-api/nodejs)

# rosette-api

This is the Rosette API client binding for R.

## Getting Started
Install the module with: `install.packages('rosetteAPI')`


## Example using the Rosette API language detection endpoint
```R
library(rosetteApi)
library(jsonlite)

parameters <- list()
parameters[[ "contentUri" ]] <- "http://www.onlocationvacations.com/2015/03/05/the-new-ghostbusters-movie-begins-filming-in-boston-in-june/"

result <- api("0123456789", "categories", parameters)
# result is a list containing content and headers in native R.  Use jsonlite::toJSON to convert to JSON format.
print(jsonlite::toJSON(result$content, pretty = TRUE)
```
## API Parameters
| Parameter                     | Endpoint                                            | Required
| -------------                 |-------------                                        |-------------
| content                    | categories, entities, language, morphology, relationships, sentences, sentiment, tokens, syntax/dependencies, transliteration (Yes)            | Either content or contentUri required |
| contentUri                      | categories, entities, language, morphology, relationships, sentences, sentiment, tokens, syntax/dependencies       | Either content or contentUri required |
| language                          | categories, entities, language, morphology, relationships, sentences, sentiment, tokens, name similarity                    | No |
| documentFile                      | categories, entities, language, morphology, relationships, sentences, sentiment, tokens                  | No |
| name1                 | name similarity               | Yes |
| name2               | name similarity| Yes |
| name    | name translation     | Yes |
| targetLanguage           | name translation, transliteration           | Yes |
| entityType                 | name translation         | No |
| sourceLanguageOfOrigin        | name translation | No |
| sourceLanguageOfUse                         | name translation       | No |
| sourceScript                     | name translation, transliteration (Yes)               | No |
| sourceLanguage | transliteration | Yes |
| targetScript                     | name translation, transliteration (Yes)                   | No |
| targetScheme                        | name translation          | No |
| options              | relationships        | No |
| accuracyMode              | relationships        | Yes |
| explain              | sentiment        | No |
| morphology             | morphology        | Yes |

## Additional Information
See [Rosette API site](https://developer.rosette.com/)
