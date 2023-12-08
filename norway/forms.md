#Chapter 9 Summary: Forms and Inputs

1. Creating a "Contact Me" section
    a. "Contact Me" should be its own article. You can id it (e.g. article id= "contact")

    b. Start with the <form> tag. The *action* attribute must be included. <form action= ">
        i.The *action* attribute tells us where we want to send the input information (typically, the server)
        ii. In Dave's example, we will send the info to a particular website - <form action= "https://httpbin.org/get"
        iii. A *method* attribute is also needed. This refers to the method being used (e.g. get vs post)

    c. Create a <label>
        i. *for* attribute needed. <label for= "firstName">First Name: </label>. Camelcase is used here. The *for* attribute must match the <input id> later

    d. Establish <input> element for adding input (if creating drop down menu, see <select> section)
    ## Used when you want the user to input data
    ### No closing tag for <input>
        i. Attribute: *type*: <input type=  "text"> Other options: "password", "tel", "number", "radio", "checkbox", "email", "submit"
        ii. Attribute: *name*: <input name=  "firstName"> This is how it is identified at the server level
        iii. Attribute: *id*: <input id=  "firstName"> Important: Must match <label for="">
        iv. Attribute: *placeholder: <input placeholder=  "Jane"> example data
        v. Attribute: *autocomplete*: <input autocomplete= "on"> Will remember previous inputs and suggest those
        vi. Attribute: *required*: you do NOT need an equal sign here. Can leave as is. Makes the label a required input
        vii. Attribute: *autofocus*: also does not need an equal sign. Only one input element can have this because you telling the browser where to start the cursor
        viii. Attribute: *pattern*: For phone numbers. <input pattern="[0-9]{3}[0-9]{3}[0-9]{4}"> 

    e. More about the input type="number"
        i. Creates an input field with up/down arrows
        ii. Can establish the following attributes: min, max, step (provides the interval between values), & value (the starting value)

    f. Establish <select> element, if appropriate. 
    ## Used when you want the user to select from a drop down menu (Dave's coffee example)
    ### There is a closing </select> for this element, unlike <input>!
        i. Provide <label> as before. An <input type> is not applicable here
        ii. Attribute: *name*: <input name=  "coffee"> This is how it is identified at the server level
        iii. Attribute: *id*: <input id=  "coffee"> Important: Must match <label for="">
        iv. Attribute: *multiple* - allows user to select multiple options. No = needed
        v. Attribute: *size*: how many options should be displayed on page (otherwise, user will scroll down)
        vi. Provide options via the <option> tag with a *value* attribute.
            ex: <option value= "latte>Latte</option>
        vii. You can provide more organization with the <optgroup> tag. Needs label that IS SEEN by user
            ex: <optgroup label= "Espresso Drinks"> .....list of <option value...>....</optgroup>
        viii. Close the <select> tag when done

    g. If desired, create a <datalist>
    ## can use instead of <select>
    ### Benefit: Creates a textbox that allows the user to start typing their answer, which filter the dropdown options
        i. Start with <label> as usual
        ii. Add a *list* attribute to input:
            ex: <input type= "text" name= "coffee" id= "coffee" list= "coffee-list">
        iii. Add a <datalist> element with an *id* attribute. The <datalist id> must match the *list* attribute name from the <input> 
            ex: <datalist id= "coffee-list">
        iv. Add <option value>. However, it'll look different than it does in the "select" option. Here is the format:
            ex: <option value= "coffee">
            Note: There is NO closing <option> tag
            Note: The user WILL SEE the name you input as the value
        v. To end, use ending <datalist> tag

    h. Adding Organization (especially with large forms) with <fieldset> and <legend>
        i. Add <fieldset> just below the <form> element
        ii. <Legend> is added to create a caption that descripes the section (e.g. Personal Info)
        iii. This will create a linebox that contains the info in the fieldset
            ex: <fieldset>
                    <legend>Personal Information</legend>
                    .....
                </fieldset>

    i. Creating Radio Buttons
    ## Create a circular select button by the option (think like choosing an answer on a test)
    ### Be careful naming ids! Do not double up within form
        i. For the radio button, the <input> will go BEFORE the <label>
        ii. <input> will use *radio* attribute.
        iii. the *name* attribute MUST match all options. In Dave's "Favorite Food" example, every name equaled "food"
        iv. the *id* and *value* input attributes will be specific to the option. So, if the option reads, "pizza, the id and value will equal pizza
        v. Add <label for>. This MUST match the input id as usual
        vi. Example of a radio button option:
                <input type= "radio" name= "food" id= "pizza" value= "pizza">
                <label for= "pizza">Pizza</label>

    j. Creating Checkbox Buttons
    ## Creates boxes; multiples checks allows
    ### Very similar to Radio Button creation
    #### Be careful naming ids! Do not double up within form
        i. For the checkbox button, the <input> will go BEFORE the <label> (just like radio buttons)
        ii. <input> will use *checkbox* attribute.
        iii. the *name* attribute MUST match all options. In Dave's "Do You Have Pets" example, every name equaled "pets"
        iv. the *id* and *value* input attributes will be specific to the option. So, if the option reads, "cat", the id and value will equal "cat"
        v. Add <label for>. This MUST match the input id as usual
        vi. Example of a checkbox button option:
                <input type= "checkbox" name= "pets" id= "cat" value= "cat">
                <label for= "cat">Cat</label>

    k. Creating a textarea
    ## Creates an area where the user can type a response/message to you in a large space
        i. Create <label for> as usual
        ii. NO INPUT ELEMENT needed
        iii. Dave places a <br> after the <label for>. Probably because he does not use the <p> element here
        iv. Create a <textarea> element with the usual *name* and *id* attributes, plus some additional attributes:
                *<cols= "30"> ....this is the default width
                *<rows= "10>" ....this is the default height
                *<placeholder= "Type your message here">
        v. <textarea> does require end tags

    l. Creating buttons
    ## Creates buttons via <button> (e.g. submit, reset)
    ### Buttons add semantic meaning (it is possible to create a "button" without a <button> tag by using input type="submit", but <button> is better)
        i. creating a button is simple because it only requires a <button> element with attributes like *type*
        ii. Submit button example: <button type= "submit">Submit</button>
        iii. Reset button example: <button type= "reset">Reset</button>
        iv. A Post button is a little more complex and is discussed in the get vs post section below. But basically, the purpose of a "post" button is to override our initial form method. 

    m. get method vs. post method
        i. Never use the get method with sensitive information because it will post all your answers into the URL
        ii. The post method does not post sensitive answers into the URL. Here is an example of how to write it:
            ex: <button type= "submit" formaction= "https://httpbin.org/post" formmethod= "post">Post</button>
        iii. Choosing this button will override our original method. We haven't fully learned why we cannot just use post to begin with

    n. Additional guidelines/thoughts:
        i. Use the MDN link for more input types! developer.mozilla.org/en-US/docs/Learn/Forms
        ii. Dave likes to place a <p> tag wrapping around the <label> and <input> duo (not around each element individually, but together)
        iii. Dave likes to use <br> between each fieldset