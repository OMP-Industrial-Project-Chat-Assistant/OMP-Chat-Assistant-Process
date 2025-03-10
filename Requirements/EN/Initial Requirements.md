Русская версия: [Изначальные Требования](<Изначальные Требования.md>) 
# Requirements
After the interview on February 21, 2025, the team came up with the following product requirements:
- The product must work on the following API:
	- A request with a question about the documentation is sent to the server
		- A Markdown file with a detailed answer on the documentation is sent in response
		- The answer must be in Russian
		- The answer must use information from the following sources:
			- Source files of the section https://developer.auroraos.ru/doc/5.1.1/software_development/guides in Markdown format
			- Files from the page https://gitlab.com/omprussia/demos
			- Files from the page https://gitlab.com/omprussia/examples
		- The answer must not contain information not related to the provided documentation
		- The answer must contain links to the used documentation pages
- The product must meet the following quality requirements:
	- Receiving a response to a request should take no more than 2 minutes (in case of deployment on a server that meets technical requirements)
	- The product must be accompanied by documentation in Russian, explaining how to:
		- Deploy the product
		- Work with the product
		- Use the product
		- Change/add content used by the product to formulate a response
	- The product should support up to 10 users making requests to the product
- The product must comply with the following restrictions:
	- The product must not use third parties' APIs or resources during operation
	- Licenses of all components used in the product must allow Aurora to use the product for commercial purposes.