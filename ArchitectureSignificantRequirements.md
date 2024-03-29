# cybuy - Architecture Significant Requirements

## Utility Tree
| Quality attribute | Quality attribute scenarios |                                |                    |                  |                                                           |                                       | Business value | Technical risk |
|-------------------|-----------------------------|--------------------------------|--------------------|------------------|-----------------------------------------------------------|---------------------------------------|----------------|----------------|
|                   | Source                      | Stimulus                       | Artifact           | Environment      | Response                                                  | Response measure                      |                |                |
| Availability      | A user                      | submits bad form               | backend controller | normal operation | send error reply                                          | don't commit bad data to the database | H              | H              |
|                   | …                           |                                |                    |                  |                                                           |                                       |                |                |
| Modifiability     | A backend developer         | wants to make a change         | backend controller | normal operation | reroute to secondary backend                              | minimal downtime                      | H              | H              |
|                   | A backend developer         | makes a mistake in production  | backend controller | update           | halt operation, restore database backup, rollback changes | reliable operation                    | H              | H              |
|                   | A frontend developer        | wants to make a change         | frontend           | normal operation | overwrite production and let angular compile              | minimal downtime                      | H              | M              |
|                   | A moderator                 | wants to delete a listing/user | database           | normal operation | communicate reasoning to buyer and seller                 | user satisfaction                     | M              | S              |
|                   | …                           |                                |                    |                  |                                                           |                                       |                |                |
| Performance       | A bad actor                 | spams requests                 | backend controller | under load       | throttling                                                | minimise load on server               | H              | M              |
|                   | …                           |                                |                    |                  |                                                           |                                       |                |                |
| Security          | A regular user              | opens url for others data      | backend controller | normal operation | access denied                                             | GDPR compliance                       | H              | H              |
|                   | …                           |                                |                    |                  |                                                           |                                       |                |                |
| Usability         | An elderly person           | does not know what to do       | frontend           | regular use      | intuitive design                                          | user retention                        | M              | S              |
|                   | …                           |

## Architecture Decisions and Design Patterns
- Using well known Front- and Backend solutions
- Mono-/Modulithic design for faster development allowed by limited target audience
- Easily bootable in a test environment
- Containerised test database to provide test data and save on configuration time for testing
