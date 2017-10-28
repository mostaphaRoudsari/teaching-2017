# teaching-2017
Student projects from 2017

### Repository structure
```
.
|-- students.json   // list of all the students in this course
|-- assignments.json // list of all the assignments and their data
|
`-- assignment_folder  // dedicated folder for each assignment
   |-- thumbnail
   |     |-- *.png // list of thumbnails for submissions generated from pdfs  
   |-- family_name_name_*.* // list of files that start with family_name_name
   `-- groups.json  // list of groups and their members only for group projects
```

### students.json

This file in generated once at the start of the semester for each course.

```js
[
  {
    "id": integer,
    "family_name": string,
    "name": string,
    "email": string
  }, ...
]
```

### assignments.json

This file will be updated every week from the submissions.

```js
[
  {
    "name": string, // assignment human readable name
    "folder": string, // assignment folder name
    "is_group_project": false, // is submission team work or not. false by default
    "submissions": [] // list of submissions. see below
  }
]
```

### submission

```js
{
  "team": [integer], // list of student ids. multiple ids for group projects
  "team_name": null, // group name if a group project, otherwise student name
  "files": [], // list of file names for this submission
  "thumbnail": null // thumbnail filename for this submission
}
```


### groups.json
Group information created manually for group projects.

```js
[
  {
    "name": string, // group name
    "members": [] // list of submissions. see below
  }
]
```

### student_info.json

This file is created automatically by parsing `assignments.json`.

```js
[
  {
      "name": string, // student name
      "family_name": string, // student family name
      "id": integer, // student id
      "submissions": [
        {
          "name": string, //submission name
          "folder": string // submission folder - useful for loading the thumbnail
        }
      ]

  }, ...

]
```
