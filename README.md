Download Link: https://assignmentchef.com/product/solved-cse225l-data-structures-and-algorithms-lab-lab-05-sorted-list-array-based
<br>
In today’s lab we will design and implement the List ADT where the items in the list are sorted.

<table width="712">

 <tbody>

  <tr>

   <td width="325"><strong>sortedtype.h </strong> #ifndef SORTEDTYPE_H_INCLUDED#define SORTEDTYPE_H_INCLUDED const int MAX_ITEMS = 5; template &lt;class ItemType&gt; class SortedType{     public :SortedType();         void MakeEmpty();         bool IsFull();         int LengthIs();void InsertItem(ItemType);         void DeleteItem(ItemType);         void RetrieveItem(ItemType&amp;, bool&amp;);void ResetList();void GetNextItem(ItemType&amp;);     private:int length;ItemType info[MAX_ITEMS];         int currentPos;};#endif // SORTEDTYPE_H_INCLUDED<strong>sortedtype.cpp </strong> #include “sortedtype.h” template &lt;class ItemType&gt;SortedType&lt;ItemType&gt;::SortedType(){     length = 0;     currentPos = – 1;} template &lt;class ItemType&gt; void SortedType&lt;ItemType&gt;::MakeEmpty(){     length = 0;} template &lt;class ItemType&gt;bool SortedType&lt;ItemType&gt;::IsFull(){     return (length == MAX_ITEMS);} template &lt;class ItemType&gt; int SortedType&lt;ItemType&gt;::LengthIs(){     return length;} template &lt;class ItemType&gt; void SortedType&lt;ItemType&gt;::ResetList(){     currentPos = – 1;} template &lt;class ItemType&gt;void SortedType&lt;ItemType&gt;::GetNextItem(ItemType&amp; item) {     currentPos++;item = info [currentPos];}</td>

   <td width="387">template &lt;class ItemType&gt;void SortedType&lt;ItemType&gt;::InsertItem(ItemType item){int location = 0;bool moreToSearch = (location &lt; length); while (moreToSearch){if(item &gt; info[location]){location++;moreToSearch = (location &lt; length);}else if(item &lt; info[location])             moreToSearch = false;}for (int index = length; index &gt; location; index–)info[index] = info[index – 1];     info[location] = item;     length++;}template &lt;class ItemType&gt;void SortedType&lt;ItemType&gt;::DeleteItem(ItemType item){int location = 0; while (item != info[location])         location++;for (int index = location + 1; index &lt; length; index++)info[index – 1] = info[index];     length–;}template &lt;class ItemType&gt;void SortedType&lt;ItemType&gt;::RetrieveItem(ItemType&amp; item, bool&amp; found){int midPoint, first = 0, last = length – 1;     bool moreToSearch = (first &lt;= last);     found = false;while (moreToSearch &amp;&amp; !found){midPoint = (first + last) / 2;         if(item &lt; info[midPoint]){last = midPoint – 1;moreToSearch = (first &lt;= last);}else if(item &gt; info[midPoint]){first = midPoint + 1;moreToSearch = (first &lt;= last);}         else         {found = true;item = info[midPoint];}}}</td>

  </tr>

 </tbody>

</table>

Generate the <strong>driver file (main.cpp) </strong>where you perform the following tasks. Note that you cannot make any change to the header file or the source file.




<table width="703">

 <tbody>

  <tr>

   <td width="362"><strong>Operation to Be Tested and Description of Action </strong></td>

   <td width="174"><strong>Input Values </strong></td>

   <td width="166"><strong>Expected Output </strong></td>

  </tr>

  <tr>

   <td width="362">        •     Create a list of integers</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print length of the list</td>

   <td width="174"> </td>

   <td width="166">0</td>

  </tr>

  <tr>

   <td width="362">        •     Insert five items</td>

   <td width="174">5  7  4  2  1</td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">1  2  4  5  7</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 6 and print whether found</td>

   <td width="174"> </td>

   <td width="166">Item is not found</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 5 and print whether found</td>

   <td width="174"> </td>

   <td width="166">Item is found</td>

  </tr>

  <tr>

   <td width="362">        •     Print if the list is full or not</td>

   <td width="174"> </td>

   <td width="166">List is full</td>

  </tr>

  <tr>

   <td width="362">        •     Delete 1</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">2  4  5 7</td>

  </tr>

  <tr>

   <td width="362">        •     Print if the list is full or not</td>

   <td width="174"> </td>

   <td width="166">List is not full</td>

  </tr>

  <tr>

   <td width="362">•     Write a class timeStamp that represents a time of the day. It must have variables to store the number of seconds, minutes and hours passed. It also must have a function to print all the values. You will also need to overload a few operators.</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Create a list of objects of class timeStamp.</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •    Insert 5 time values in the format ssmmhh</td>

   <td width="174">15   34   2313   13   0243   45   1225   36   1752   02   20</td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •    Delete the timestamp 25   36   17</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">15:34:2313:13:0243:45:1252:02:20</td>

  </tr>

 </tbody>

</table>


