blank and null in Django fields
-------------------------------

See http://stackoverflow.com/a/8159520

Default: 
* blank=False, null=False

CharField and TextField send '' rather than NULL to DB when empty. Never set null=True or you'd have two kinds of empty values

When change default: 

* blank=True, null=True
  * General: It's OK for non Char/Text fields
  * CharField or TextField: never set null=True 

* blank=True, null=False 
  * General: will raise IntegrityError anytime the field is left blank
  * CharField or TextField: It's OK. will save '' if field is left blank 

* blank=False, null=True 
  * General: will always require the field to be filled out in all forms (forms will raise ValidationError on the field), even though the column is allowed to be NULL. However, this only applies to forms. You could manually set the attribute to None and save it outside of a form (in the shell, for example).
  * CharField or TextField: never set null=True 
