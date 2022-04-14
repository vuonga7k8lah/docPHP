# Type Elementor

* [1.Text](#1test)
* [2.Number](#2number)
* [3.Textarea](#3textarea)
* [4.Wysiwyg](#4wysiwyg)
* [5.Code](#5code)
* [6.Hidden](#6hidden)
* [7.Switcher](#7switcher)
* [8.Toggle](#8toggle)
* [9.Select](#9select)
* [10.Select2](#10select2)
* [11.Choose](#11choose)
* [12.Color](#12color)
* [13.Icons](#13icons)
* [14.Font](#14font)
* [15.DateTime](#15dateTime)
* [16.Gallery](#16gallery)
* [17.Array](#17array)
* [18.Tabs](#18tabs)
* [19.Tab](#19tab)
* [20.Session](#20session)

## 1.test

#### Arguments

````ts
export interface Text {
    label: string
    title: string
    id: string
    name: string
    type: text
    default: string
    placeholder: string
}

````

#### Example

````json
{
  "name": "settings",
  "id": "title3455dd4311",
  "label": "Settings",
  "type": "text",
  "default": "test hihi",
  "placeholder": "string"
}

````

## 2.number

#### Arguments

````ts
export interface Number {
    label: string
    title: string
    id: string
    name: string
    type: number
    default: string
    placeholder: string
    min: string
    max: string
}

````

#### Example

````json
{
  "name": "number-test",
  "id": "xfd455dd4311",
  "label": "Number test",
  "type": "number",
  "default": "2",
  "max": "6",
  "min": "1",
  "placeholder": "Lorem Ipsum is simply dummy text of the printing and typesetting industry"
}

````

## 3.textarea

#### Arguments

````ts
export interface Textarea {
    label: string
    name: string
    rows: int
    type: textarea
    default: string
    placeholder: string
    description: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Description",
  "type": "textarea",
  "default": "Default description",
  "rows": 10,
  "placeholder": "Lorem Ipsum is simply dummy text of the printing and typesetting industry"
}

````

## 4.wysiwyg

#### Arguments

````ts
export interface Wysiwyg {
    label: string
    name: string
    type: wysiwyg
    default: string
    placeholder: string
    description: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Description",
  "type": "wysiwyg",
  "default": "Default description",
  "placeholder": "Lorem Ipsum is simply dummy text of the printing and typesetting industry"
}

````

## 5.code

#### Arguments

````ts
export interface Code {
    label: string
    id: string
    name: string
    language: string // default html
    type: code
    rows: 10
    default: string
    description: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Description",
  "type": "code",
  "language": "php",
  "rows": 20,
  "default": "Default description"
}

````

## 6.hidden

````ts
export interface Hidden {
    label: string
    id: string
    name: string
    type: hidden
    default: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Description",
  "type": "hidden",
  "default": "Default description"
}

````

## 7.switcher

````ts
export interface Switcher {
    label: string
    id: string
    name: string
    type: switcher
    default: string
    description: string
    label_on: string
    label_off: string
    return_value: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Show Title",
  "type": "switcher",
  "label_on": "Show",
  "label_off": "Hide",
  "return_value": "yes",
  "default": "yes"
}

````

## 8.toggle

````ts
export interface Toggle {
    label: string
    id: string
    name: string
    type: toggle
    default: string
    description: string
    label_on: string
    label_off: string
    return_value: string
}

````

#### Example

````json
{
  "id": "xfd455dd4311",
  "name": "xfd455dd4311",
  "label": "Show Title",
  "type": "switcher",
  "label_on": "Show",
  "label_off": "Hide",
  "return_value": "yes",
  "default": "yes"
}

````

## 9.select

````ts
export interface Select {
    label: string
    id: string
    name: string
    type: select
    default: string
    description: string
    options: object
}

````

#### Example

````json
{
  "id": "xfd455dssd4311",
  "name": "xfd455dssd4311",
  "label": "Border Style",
  "type": "select",
  "options": {
    "solid": "Solid",
    "dashed": "Dashed",
    "dotted": "Dotted"
  },
  "default": "solid"
}

````

## 10.select2

````ts
export interface Select2 {
    label: string
    id: string
    name: string
    type: select2
    default: string | object
    description: string
    multiple: boolean
    options: object
}

````

#### Example

````json
{
  "id": "xfd455dssd4311",
  "name": "xfd455dssd4311",
  "label": "Border Style",
  "type": "select2",
  "multiple": true,
  "options": {
    "solid": "Solid",
    "dashed": "Dashed",
    "dotted": "Dotted"
  },
  "default": [
    "dashed",
    "solid"
  ]
}

````
## 11.choose

````ts
export interface Choose {
    label: string
    id: string
    name: string
    type: choose
    default: string
    description: string
    toggle: boolean
    options: object
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Alignment",
  "type": "choose",
  "toggle": true,
  "options": {
    "center": {
      "title": "Center",
      "icon": "eicon-text-align-center"
    },
    "left": {
      "title": "Left",
      "icon": "eicon-text-align-left"
    },
    "right": {
      "title": "Right",
      "icon": "eicon-text-align-right"
    }
  },
  "default": "center"
}

````

## 12.color

````ts
export interface Color {
    label: string
    id: string
    name: string
    type: color
    default: string
    description: string
    alpha: boolean
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Title Color",
  "type": "color"
}

````

## 13.icons

````ts
export interface Icons {
    label: string
    id: string
    name: string
    type: icons
    default: string
    description: string
    include: object
    exclude: object
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Title Color",
  "type": "icons"
}

````

## 14.font

````ts
export interface Font {
    label: string
    id: string
    name: string
    type: font
    default: string
    description: string
    options: object
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Title Color",
  "type": "font",
  "default": "Open Sans",
  "selectors" : {
    "{{WRAPPER}} .title":"font-family: {{VALUE}}"
  }
}

````
## 15.dateTime

````ts
export interface DateTime {
    label: string
    name: string
    id: string
    type: font
    default: string
    description: string
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Title Color",
  "type": "dateTime"
}

````

## 16.gallery

````ts
export interface Gallery {
    label: string
    id: string
    name: string
    type: gallery
    default: string
    description: string
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Add Images",
  "type": "gallery",
  "default": []
}

````
## 17.array

````ts
export interface Array {
    label: string
    id: string
    name: string
    type: array
    default: string | []
    description: string,
    fields : [] // mảng các fieids
}

````

#### Example

````json
 {
  "id": "test-array",
  "name": "test-array",
  "label": "TEST ARRAY",
  "type": "array",
  "required": false,
  "default": [
    {
      "test-icons": "test abc ",
      "test-title": "xxxxx ",
      "test-price": "test price ",
      "test-wysiwyg": "test price "
    }
  ],
  "fields": [
    {
      "label": "Test Icons",
      "id": "test-icons",
      "name": "test-icons",
      "type": "icons",
      "required": false
    },
    {
      "id": "test-title",
      "name": "test-title",
      "label": "Title",
      "type": "text",
      "required": true
    },
    {
      "id": "test-price",
      "name": "test-price",
      "label": "Price",
      "type": "text",
      "required": true
    },
    {
      "id": "test-wysiwyg",
      "name": "test-wysiwyg",
      "label": "TEST wysiwyg",
      "default": "TEST wysiwyg",
      "type": "wysiwyg"
    }
  ]
}

````
## 18.tabs

````ts
export interface Tabs {
    label: string
    id: string
    name: string
    type: gallery
    default: string
    default: string | []
    description: string,
    fields : [] // mảng các fieids
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Add Images",
  "type": "gallery",
  "default": []
}

````
## 19.tab

````ts
export interface Tab {
    label: string
    id: string
    name: string
    type: gallery
    default: string | []
    description: string,
    fields : [] // mảng các fieids
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Add Images",
  "type": "gallery",
  "default": []
}

````
## 20.session

````ts
export interface Session {
    label: string
    id: string
    name: string
    type: gallery
    default: string | []
    description: string,
    fields : [] // mảng các fieids
}

````

#### Example

````json
{
  "id": "xfd45ss5dssd4311",
  "name": "xfd45ss5dssd4311",
  "label": "Add Images",
  "type": "gallery",
  "default": []
}

````
