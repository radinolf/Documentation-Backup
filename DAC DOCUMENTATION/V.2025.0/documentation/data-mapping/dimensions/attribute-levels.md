# Attribute levels

On each level created it is possible to associate attributes, through the _**Select levels as attributes**_ item of the pop-up menu. The levels attributed will be used in the report, similarly to the normal levels, but will not contribute to the definition of the hierarchy, making the construction easier.

The attributes of a dimensional level are defined in the following way:

1. Create the dimensional level using the multiple-selection mode . One or more fields can be selected to map both the parent level and the attributes.
2. Open, on the main dimensional level, the pop-up menu (right button) and select _**Select levels as attributes:**_ a pop-up opens which shows all the levels mapped on the same table (those chosen in the next step).
3. Select the levels you want to set as attributes
4. Close the pop-up: the _attribute_ _levels_ appear indented compared to the main one

The **parent-name** property (in the **Property** section,**)** allows the level it is an attribute of, to be displayed.

Example: Dimensional Level Attribute

Step 1: Creating a Level and Its Attributes![](/broken/files/-MeULeJwmb9kGuDC5s52)



![](<../../../.gitbook/assets/image (1042).png>)

_In the example, the customer dimension must be created, with the Client level having the information on the address, the telephone number and the city as attributes. All the data is in the SM\_LK\_CUSTOMER table._

_A multiple selection of the main level (DS\_CUSTOMER) and its attributes is performed (ADDRESS, CITY and PHONE\_NO)._

_Right-click on the main level and the pop-up menu appears. When selecting the item Select levels as attributes, the pop-up opens with the previously mapped levels, on the same table._

Step 2: Creating a Level and Its Attributes

![](<../../../.gitbook/assets/image (1815).png>)

_By selecting the levels as attributes, when the pop-up closes, the attribute levels will be indented under the main one._
