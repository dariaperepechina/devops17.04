# devops17.04
 При запуске возникает ошибка:
AttributeError: module 'wtforms.validators' has no attribute 'required'

Для ее решения предлагаю в forms.py 7 и 8 строчки:
username = StringField('Username:', validators=[validators.required(), validators.Length(min=1, max=30)])
    password = StringField('Password:', validators=[validators.required(), validators.Length(min=1, max=30)])
исправить на:
username = StringField('Username:', validators=[validators.DataRequired(), validators.Length(min=1, max=30)])
    password = StringField('Password:', validators=[validators.DataRequired(), validators.Length(min=1, max=30)]) 
или
username = StringField('Username:', validators=[validators.InputRequired(), validators.Length(min=1, max=30)])
    password = StringField('Password:', validators=[validators.InputRequired(), validators.Length(min=1, max=30)]) 

