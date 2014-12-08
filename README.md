Lazybones templates for java and groovy projects
--------------------------

Templates from this project can be used by [lazybones](https://github.com/pledbrook/lazybones).

## List of templates

  * [java-springmvc-swagger-heroku](#java-springmvc-swagger-on-heroku-template)

## Installation and configuration

1. Add new repository to `~/.lazybones/config.groovy`. *pledbrook/templates* is default and standard set of templates.

    ```groovy
    bintrayRepositories = [
      "pledbrook/lazybones-templates",
      "zedar/templates"
    ]
    ```

2. List of availbale templates

    $ lazybones list

3. Create new application from template

    $ lazybones create <template-name> <version> <new-project-dir-name>

## Java SpringMVC Swagger on Heroku Template

1. Create new project structure

    $ lazybones create java-springmvc-swagger-heroku new-project-dir

2. Enter project folder

    $ cd new-project-dir

3. Run the project

    $ ./gradlew run
    $ curl -X GET http://localhost:9090/api-docs

4. Deploy to heroku

    $ heroku login
    $ heroku create api-test
    $ git push heroku master

## Templates deployment

You have just created a simple project for managing your own Lazybones project
templates. You get a build file (`build.gradle`) and a directory for putting
your templates in (`templates`).

To get started, simply create new directories under the `templates` directory
and put the source of the different project templates into them. You can then
package and install the templates locally with the command:

    ./gradlew installAllTemplates

You'll then be able to use Lazybones to create new projects from these templates.
If you then want to distribute them, you will need to set up a Bintray account,
populate the `repositoryUrl`, `repositoryUsername` and `repositoryApiKey` settings
in `build.gradle`, add new Bintray packages in the repository via the Bintray
UI, and finally publish the templates with

    ./gradlew publishAllTemplates

You can find out more about creating templates on [the GitHub wiki][1].

[1]: https://github.com/pledbrook/lazybones/wiki/Template-developers-guide
