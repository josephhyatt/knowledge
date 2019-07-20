# MVC



![](../../../.gitbook/assets/mvc_rails.png)

> A **user** who sees the `view` of the **application** in the `browser` and it can make a **request** with **input** to a `router` \(a request can me a `link` that gets clicked\). The `router` will **call** a specific `controller method` based on that `route`, and if **data** is needed to be **fetched** the `controller` will then interact with the  `model`, which interacts with the `database`. Once the `controller` gets that data **passed back** it can then load a `view` and it can **send the data** to the `view` and will be **dealt with** by the `template engine`. Once that is all done, it will **send** the `view` back to the `browser` for the user to see.

## Model

> Responsible for **getting** and **manipulating** the **data**. The **brain** of the **application**. The model usually interacts with some kind of **database** `MySQL/ MongoDB`

* Data related logic
* Interactions with database `SELECT, INSERT, UPDATE, DELETE`
* Communicates with **Controller**

## View

> Is the **user interface** with the application \(**what the users sees**\).

* What the end user sees `UI`
* Usually consists of `HTML/CSS`
* Communicates with the **controller**
* Can be passed dynamic values from the controller
* **Template Engines** - allows **dynamic data**  \(the use `variables` or `logic`\) inside of `views`
  * **Examples** - `ERB` \(Embedded Ruby\),  `Haml`

## Controller

> Acts as a **middleman** between the `model` and the `view` . The controller will **ask** the `model` to get some **data** from the **database** and the controller will take that data and **load a** `view` and **pass** that data into it. Then the **template engine** takes over and do some **logic** or **output** for the **variables and things like that. The controller can also** load **a** `view` **without** passing it data.

* Receives input from `view`, `URL`
* Processes requests `GET` `POST` `PUT` `DELETE`
* **Gets data**  from the `model`
* **Passes data** to the `view`

