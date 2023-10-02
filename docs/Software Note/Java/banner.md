## Banner.txt

````
1. Regarding Spring in banner.txt, it can be automatically recognized, but if it is not displayed, directly check whether it is in the target. If not, put it in directly! ! !
2. The configuration items related to spring.banner.image.* in SpringBoot3 have been deprecated, this function has been removed, and only text files are supported to generate Banner.
3. Recommended banner pattern generation website: http://patorjk.com/software/taag/ Just click Test ALL to display all styles.
4. ${AnsiColor.BRIGHT_RED}: Set the color of the output content in the console to red
5. ${application.version}: used to obtain the version number in the MANIFEST.MF file
6. ${application.formatted-version}: Formatted ${application.version} version information
7. {spring-boot.version}: Spring Boot version number
8. ${spring-boot.formatted-version}: Formatted version information of ${spring-boot.version}
````
