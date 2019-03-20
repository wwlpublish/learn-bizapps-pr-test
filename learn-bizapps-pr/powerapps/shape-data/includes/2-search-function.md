The Filter function works great when you want to make very specific, and
often static queries. Use the Search function when you would like to do
a more flexible query against a string column. A common use case is
providing a search input box to allow the app user to type in a string
and then your gallery will return records that match the string anywhere
within the column.

An example would be if you wanted to do a partial string match on an
address column. If the column was a text column called Address and you
had a Text Input control in your app named SearchInput, then you could
use the following formula in the Items property of a gallery.

```
Search(YourDataSource, SearchInput.Text, "Address")
```

This would return all the records where the Address column contained the
value entered in the **Text Input** control SearchInput. Another useful
behavior is if SearchInput is blank, meaning the user has not entered
any data, then all the records from YourDataSource would be returned.
This makes the Search function very powerful and easy to use.

The Search function can also be used to search across more than one
column. To have the previous example also search in the text column
City, you would update the formulas as follows.

```
Search(YourDataSource, SearchInput.Text, "Address", "City")
```

By adding a comma, and then an additional text column you are now
searching a second column. You can add as many additional text columns
as needed.
 