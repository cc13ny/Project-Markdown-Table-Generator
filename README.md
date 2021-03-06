# Project Markdown Table Generator

The *Project Markdown Table Generator* reads project data from `projects.json` and generates stylish markdown tables in the file `OutstandingProjects.md`. [Check out a sample here. ](./OutstandingProjects.md)

>**Note:** Code only tested on OSX with python pre-installed.

![](./resource/screenshot.png)

## Run the script

The python script reads `projects.json` and generates markdown tables in `OutstandingProjects.md`.
```
python ./scripts/md_table_generator.py
```

## projects.json

The `projects.json` should be in the same folder as `md_table_generator.py` and provide these properties `name`, `category`, `project_url`, `team`, `description`, `stack` as the example shown below.

```
{
   "projects":[
      {
         "name":"wukong",
         "category":[
            "full stack"
         ],
         "project_url":"https://github.com/BitTigerInst/wukong",
         "team":"BJGX(白驹过隙)",
         "description":"Platform for BitTiger",
         "stack":[
            "nodejs",
            "angular",
            "mongodb"
         ]
      },
      {
         "name":"Crawler-bitTiger",
         "category":[
            "full stack"
         ],
         "project_url":"https://github.com/BitTigerInst/Crawler-bitTiger",
         "team":"BJGX(白驹过隙)",
         "description":"Crawer for wukong",
         "stack":[
            "nodejs"
         ]
      }
   ]
}
```
#### Category Property

`category` means the project category in the JSON file. Currently, only `full stack`, `mobile` and `big data` are supported in this field. If a project lists `full stack` as one of its categories, it will show up in the *Full Stack* project markdown table. As suggested by the JSON array syntax, one project may have more than one category.


#### Stack Property

`stack` property in the JSON file means the project's technology stack. Each item in the array will be replaced with a corresponding icon in the table. The script generates html image tags `<img>...</img>` to link corresponding icons. For example, a `nodejs.png` will be embedded in the table if the `stack` property contains `nodejs`. Therefore, all items inside the `stack` property should match the exsiting file names in the folder `resource/icons`.

Only following items are supported at this moment:

>android
angular
aws
big\_data
boostrap
cordova
css
docker
firebase
flask
github
grunt
html5
ios
java
javascript
jquery
meteor
mongodb
mysql
nodejs
python
react
reddis
ruby\_on\_rails
ruby
spark
spring\_mvc
tomcat
windows

## License
Code released under the [MIT](https://opensource.org/licenses/MIT) license. (官人随意……)

