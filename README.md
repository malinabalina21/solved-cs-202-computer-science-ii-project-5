Download Link: https://assignmentchef.com/product/solved-cs-202-computer-science-ii-project-5
<br>



<strong> </strong>







<strong>Objectives:  </strong>The main objectives of this project is to test your ability to create and use inheritance with C++ classes. A review of your knowledge to manipulate classes with multiple constructors, static members/functions, and expand to operator overloading , as well as pointers, structs, arrays, iostream, file I/O and C-style strings is also included.

<strong>Description: </strong>

For this project you may use <strong>square bracket</strong>-indexing, <strong>pointers</strong>, <strong>references</strong>, all <strong>operators</strong>, as well as the <strong>&lt;string.h&gt;</strong> or <strong>&lt;cstring&gt;</strong> library functions (however the <u>std::string</u> type is still <u>not allowed</u>).




The required functionality is as follows: You are given the specifications for a 2 Classes that have an Inheritance relationship – one being the Base class (<strong>Vehicle</strong>) and one the Derived (<strong>Car</strong>). You have to translate these specifications into class implementations (header and source files) and test them against a test driver (<strong>proj5.cpp</strong>) which is provided. You are also required to explain in your documentation the observed output from running the test driver.




<strong> </strong>

<strong>The Vehicle Class will contain the following <u>protected</u> data members: </strong>

<ul>

 <li><strong>m_lla</strong>, a <u>float</u><u> array</u> of size 3 which represents the location of the vehicle on the earth (LLA stands for longitude-Latitude-Altitude, which are the 3 values stored within the array).</li>

 <li><strong>m_vin</strong>, a <u>const int</u>which represent a unique VIN – Vehicle Identification Number (no two vehicles can ever exist with the same m_vin).</li>

</ul>

<strong>and the following <u>private</u> data members:</strong>

<ul>

 <li><strong>s_idgen</strong>, a <u>static int</u> which is used by the class to generate a unique identifier to initialize m_vin whenever a new Vehicle object is instantiated – how can you achieve this behavior? (<em>Hint</em>: Remember how you have been using static variables so far to keep track of the count of a class’ active objects).</li>

</ul>

<strong>and will have the following <u>public</u> methods: </strong>

<ul>

 <li><strong>Default Constructor</strong> – will leave everything uninitialized (except m_vin which has to follow the above described specifications). When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: Default-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Parameterized Constructor</strong> – will create a new object based on a desired value for the VIN passed by-Value (it is however able to assign a different value if it runs into any danger of assigning conflicting values), and a desired set of values for LLA passed by-Address (a pointer to float data). When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: Parametrized-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Copy Constructor </strong>– will create a new object based on the values of another Vehicle object (except m_vin which has to follow the above described specifications). When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: Copy-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Destructor </strong>– called whenever an object gets destroyed. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: Dtor”</u> (where vin the actual member value).

<ul>

 <li><strong>Assignment operator</strong> – will assign member values to the calling object based on the values of another Vehicle object. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: Assignment”</u> (where vin the actual member value).

<ul>

 <li><strong>Get/Set methods </strong>as appropriate for data members m_vin and m_lla.</li>

 <li><strong>A Move </strong>method which takes in a new LLA location by-Address (a pointer to float data) in order for the Vehicle object to move there. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Vehicle #vin: CANNOT MOVE – I DON’T KNOW HOW”</u> (where vin the actual member value).

The Vehicle is a more general super-Class: It does have its own data and a number of behaviors, and it does have a function to move (the function describes a moving behavior as it takes in a new LLA location), it just implements the behavior in this limited way.

<ul>

 <li><strong>A GetIdgen</strong> static member function to return the value of the static member variable s_idgen.</li>

</ul>

<strong>You should also provide an overload for this class for the:</strong>

<ul>

 <li><strong>Insertion operator. </strong>When it gets called, it should produce an output:</li>

 <li><u>“Vehicle #vin @ [lon, lat, alt]”</u> (where vin the actual member value and lon, lat, alt the LLA[0-2] values).</li>

</ul>




<strong>The Car Class will inherit from Vehicle and will contain the following <u>private</u> data members: </strong>Ø <strong>m_plates</strong>, a C-string char array of 255 max characters (car license plates) Ø <strong>m_throttle</strong>, an int (throttle command to bring it into motion).

<strong>and will have the following <u>public</u> methods: </strong>

<ul>

 <li><strong>Default Constructor</strong> – will set a default value of 0 to m_throttle and leave the rest uninitialized. Otherwise, it should behave the same as the Vehicle Default constructor. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Car #vin: Default-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Parameterized Constructor</strong> – will create a new object based on a desired value for the license plates passed as a C-string (pointer to char data), the VIN passed by-Value (same behavior as the Vehicle Parametrized), and a desired set of values for LLA passed by-</li>

</ul>

Address (a pointer to float data). When it gets called, it should produce a debug output:

<u>“Car #vin: Parametrized-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Copy Constructor </strong>– will create a new object based on the values of another Car object (same behavior as the Vehicle Assignment). When it gets called, it should produce a debug output:</li>

</ul>

<u>“Car #vin: Copy-ctor”</u> (where vin the actual member value).

<ul>

 <li><strong>Destructor </strong>– called whenever an object gets destroyed. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Car #vin: Dtor”</u> (where vin the actual member value).

<ul>

 <li><strong>Assignment operator</strong> – will assign member values to the calling object based on the values of another Car object. When it gets called, it should produce a debug output: <u>“Car #vin: Assignment”</u> (where vin the actual member value).</li>

 <li><strong>Get/Set methods </strong>as appropriate for data members m_plates and m_throttle.</li>

 <li><strong>A Drive </strong>method which takes in a an int by-Value and uses it as a throttle value by setting it to m_throttle (begins driving at this throttle level).</li>

 <li><strong>A Move </strong>method which takes in a new LLA location by-Address (a pointer to float data) in order for the Car object to move there. When it gets called, it should produce a debug output:</li>

</ul>

<u>“Car #vin: DRIVE to destination, with throttle @ 75 “</u> (where vin the actual member value).

and then calls Drive with an argument value 75.

The Car is a more specialized sub-Class: It inherits all the data and all behaviors from Vehicle, but it can also override behaviors such as move (the function that describes a moving behavior as it takes in a new LLA location), and implements it in its own specialized way, i.e. by Drive()-ing.

<strong>You should also provide an overload for this class for the:</strong>

<ul>

 <li><strong>Insertion operator. </strong>When it gets called, it should produce an output:</li>

</ul>

<u>“Car #vin Plates: plates, Throttle: throttle @ [lon, lat, alt]”</u> (where vin the actual member value, plates the actual license plates C-string, throttle the actual throttle member value, and lon, lat, alt the LLA[0-2] values).




<strong> </strong>

<strong>The following minimum functionality and structure is required: </strong>

<ul>

 <li>You are free to use <strong>pass by-Value, pass by-Reference</strong>, <strong>pass by-Address</strong> for your function parameters.</li>

 <li>You are free to <strong>return by-Value, return by-Reference</strong>, <strong>return by-Address</strong> from your functions.</li>

 <li><strong>Pointers</strong>, <strong>References</strong>, <strong>Square Brackets</strong>-based indexing are all allowed for array (or generally any other data) manipulation.</li>

 <li>Usage of all <strong>Built-in Operators</strong> is freely allowed.</li>

 <li><strong>Const-correctness</strong> (appropriate usage of the keyword <strong>const</strong>) is expected.</li>

 <li>You may use the <strong>&lt;cstring&gt;</strong> library functions for C-string manipulation. You are not allowed to use the std::string data type.</li>

 <li>Examine the output of the provided <strong>cpp</strong> test driver for each Base and Derived class function call made. <strong>Explain </strong>what you see in your documentation file.</li>

</ul>




<strong>Try building this project using a Makefile  </strong>

<strong>            </strong>It is not imperative yet, but it will help you figure out how to address it early on before any future projects that require it. Take a look at the one provided for Lab_5 to get a head start.

<strong> </strong>

<strong>The completed project should have the following properties: </strong> Ø Written, compiled and tested using Linux.

<ul>

 <li>It must compile successfully using the g++ compiler on department machines. Instructions how to remotely connect to department machines are included in the Projects folder in WebCampus.</li>

 <li>The code must be commented and indented properly.</li>

</ul>

Header comments are required on all files and recommended for the rest of the program. Descriptions of functions commented properly.

<ul>

 <li>A one page (minimum) typed sheet documenting your code. This should include the overall purpose of the program, your design, problems (if any), and any changes you would make given more time.</li>

</ul>

<strong> </strong>

<strong>Turn in:</strong> Compressed .cpp file and project documentation.




<strong>Submission Instructions: </strong>

<ul>

 <li>You will submit your work via WebCampus</li>

 <li>The code file proj5.cpp is already provided and implements a test driver.</li>

 <li>If you have header file, name it proj5.h</li>

 <li>If you have class header and source files, name them as the respective class (Vehicle.h Vehicle.cpp Vehicle.h Vehicle.cpp) This source code structure is now mandatory.</li>

 <li>Compress your:

  <ol>

   <li>Source code</li>

   <li>Documentation</li>

  </ol></li>

</ul>

Do not include executable  Ø Name the compressed folder:

PA#_Lastname_Firstname.zip

([PA] stands for [ProjectAssignment], [#] is the Project number)  Ex: PA5_Smith_John.zip




















