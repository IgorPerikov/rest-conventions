# tips

1. Resource http://domain.com/countries/russia/cities/moscow means that we should handle all resources along the way, such as :

  * http://domain.com/countries/russia/cities
  * http://domain.com/countries/russia
  * http://domain.com/countries
  * http://domain.com
2. Updates & creation should return a resource representation
3. Pretty print response by default
4. GZip support
5. Wrap exceptional response in [JsonProblem](https://tools.ietf.org/html/draft-nottingham-http-problem-03)
