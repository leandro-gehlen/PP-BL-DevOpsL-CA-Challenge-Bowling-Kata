# Bowling Challenge - Personal Project  

### Domain Rules

![image 1 (1)](https://user-images.githubusercontent.com/114420790/201217071-4fac7d68-ed54-4b41-a32e-857052025324.png)
----

## Repo Notation:   

+ **PP** - Personal Project  
  
+ **BL** - Backend Learning  
  
+ **DevOpsL** - DevOps Learning  
  
+ **CA** - Clean Architecture  
----

# Let´s Start!  

## Why CI first?    

What I´m trying to do is to hands-on every thing that I´ve learned so far.
So, **it must be a CI/CD working enviroment.**  

If I just code the app and them put it on this CI/CD pipeline, I´ll not achieve the objective because I´ll not going to keep deploying after the app is ready for deploy.
**So, I´ve decided to build the CI first.**  

## Continuous Integration - CI  

### At CI I must check the lint and run the unit tests on every commit to dev branch.  

+  For that, I´ll be creating a Github Action that does that.
 + Runs the lint 
 + Runs the tests  

 # Learning how GitHub Action Works  

## .github and workflows Folders

+ First thing we must know, is that Github Actions looks for a .github folder inside your project.  

So, lets create it with bash command: 

``` mkdir .github ```

Now, lets push to main branch.

``` 
 > git add . 
 > git commit -m "creating .github folder as Github Action requires" 
 > git push o main
```

Inside .github folder, we must create oneother folder called workflows.
Every YAML file that will be in this workflows folder will be an action of github action.

```
> cd .github 
> mkdir workflows

```
That´s it. We now are able to create our github actions just by addind YAML files on the workflows folder!

Lets create our first action by creating an YAML file inside workflows folder.

```
>cd workflows
> touch test.yml 

```
```
> git add .
> git commit -m "workflows folder created inside .github folder as required for Github Actions.Also I´ve created an YAML file called test.yml"
> git push o main
```
## THE YAML file 

What YAML mean? 
+ YAML is not a makup language 
+ Yet another markup language

YAML is very similar to JSON files, but it uses identation. It´s also a data file that transfer data between systems.But YAML is more complex then JSON.

## Learning YAML Syntax

+ **Basic Syntax**

```
> // JSON
> //identation doesn´t matter
>   {
>        "name": "myname",
>        "age": "myage",
>       "address": "myAddress"
>   }
>
> // YAML
> //At YAML , identation is very import as it is for python!
>
> name:myname
> age:myage
> address:myaddress
>

```
+ **Nested Objects**  

```
> //JSON
> {
>   "first-level-param": {
>        "name": "myname",
>        "age": "myage",
>        "address": "myAddress"           
>      }
> }
>
> //YAML 
> 
> first-level-param:
>   name:myname
>   age:myage
>   address:myaddress
>
```
+ **Comments / Arrays / Data Types in YAML**  

```

> //JSON
> // JON can not have comments
> {
>   "first-level-param": {
>        "name": "myname",
>        "age": "myage",
>        "address": "myAddress" ,
>        "randomArray": [1,2,3,4,5,6], 
>        "randomArray-of-Objects":[ 
>               {
>                  "key1": "value1",
>                  "another-key1":"another-value1",
>                  "key1-again": "value1-again",
>                  "last-key1":"last-value1"
>                },
>                {
>                   "key2": "value2",
>                   "another-key2":"another-value2",
>                   "key2-again": "value2-again",
>                   "last-key2":"last-value2"
>                },
>                {
>                   "key3":"value3",
>                },
>                {
>                   "key4":"value4"
>            ]
>      
> }
>
> //YAML 
> //At YAML you can have comments by using the # symbol
> 
> first-level-param:  #This is a YAML comment
>   name:myname
>   age:myage
>   address:myaddress
>   randomArra: [1,2,3,4,5,6] # At YAML you can have arrays just like json, but...
>   randomArray-of-Objects: 
>        -key1: value1    # At YAML , the - represents the start of an array element.
>        another-key1:another-value1
>        key1-again: value1-again
>        last-key1:last-value1
>       -key2: value2   # new item of the array
>        another-key2 : "another-value2"  # At YAML , you can write strings with double quote, single quote, and no quote.
>        key2-again : 'value2-again'
>        last-key2 : true
>       -key3:value3
>       -key4: value4  #Last item of the array.
>       -key5: |  
>           over here
>           you can have a 
>           multiple line
>           string 
>           because you used the | (pipe) 
>           That´s how you write multiple lines strings on YAML
>

```

## YAML Validation - www.yamllint.com and Others on Google  

+ When you are writing YAML files, it´s nice to have a validator open so you can verify is your YAML file is well written.  

[Another YAML validator found online](https://codebeautify.org/yaml-validator)  

## Other

As you can see, creating a github action is very ease!
So, the thruth is that GitHub actions is all about knowing how to create YAML files with the right configurations!

So, for now on, it´s not yaml file, it´s THE YAML file!
Because it is the action it self.

## Learning about THE YAML file options

 

## Clean Architecture - Entities  

+ Mach
+ player
+ frames
+ pins  
+ frameScore 
+ PlayersRanking

## Clean Architecture - Use Cases  

+ Player gives his name and start a mach
+ Player can abandon the mach
+ A player can only play one match.
+ A mach has 10 frames
+ A player has two shots on every frame.
+ The result of a frame can be :  
 + Spare: all 10 pins in two tries.
    + Bonus: Number of pins knocked down on the next roll  
 + Strike: all 10 pins in the first try
    + Bonus: Number of pins knocked down on the next two rolls


