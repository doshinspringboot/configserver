# configserver

Reference :
	https://spring.io/guides/gs/centralized-configuration/
	https://cloud.spring.io/spring-cloud-config/multi/multi__spring_cloud_config_server.html

	1. Learning
		a. How its works
			i. Have EnvironmentRepository serving Environment objects
			ii. This Environment is a shallow copy of the domain from the Spring Environment
			iii. parametrized by three variables:
				1) {application} maps to "spring.application.name" on the client side;
				2) {profile} maps to "spring.profiles.active" on the client (comma separated list); and
				3) {label} which is a server side feature labelling a "versioned" set of config files.
		b. Property precedence
			1) active profiles take precedence over defaults
			2) if there are multiple profiles the last one wins
		c. Label with /
			1) Replaced by _
		d. Pattern Matching and Multiple Repositories
		e. Support for multiple teams
		f. Support auth basic auth
			1) 
		g. Change temp dir - spring.cloud.config.server.git.basedir 
		h. Vault Backend - spring.profiles.active=vault
			1) Connects to vault at http://127.0.0.1:8200
			2) 
		i. JDBC Backend
			
				
			

	1. Configurations
		a. Server
			i. Configuration
				1) @EnableConfigServer
				2) Git uri in config server - spring.cloud.config.server.git.uri
				3) One repo per application - https://github.com/myorg/{application}
		b. Client should have 
			i. Config
				1) @EnableConfigClient
				2) spring.application.name in bootstrap.yml
				3) Spring.profiles.active for the profiles

URL
	1. Properties - http://localhost:8888/{appname}/{profile}
