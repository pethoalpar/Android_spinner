<H1>Android spinner example.</H1>

<H3>In the activity_main.xml</H3>

```xml
<Spinner
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:id="@+id/spinner"
android:layout_alignParentTop="true"
android:layout_centerHorizontal="true" />
```

<H3>In the MainActivity.java</H3>

```java
Spinner spinner = (Spinner) this.findViewById(R.id.spinner);
       
List<String> list = new ArrayList<>();
list.add("ABC");
list.add("BCD");
list.add("CDE");
list.add("DEF");

ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,R.layout.support_simple_spinner_dropdown_item,list);
spinner.setAdapter(adapter);
spinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
      @Override
      public void onItemSelected(AdapterView<?> parent, View view, int position, long id) {
            Toast.makeText(getActivity(), parent.getItemAtPosition(position).toString(),Toast.LENGTH_LONG).show();            
      }

      @Override
      public void onNothingSelected(AdapterView<?> parent) {
      }
);    
```
