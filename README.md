# Character in last String
Ejemplo de como agregar un caracter en un string al final

```java
@Override
public void onTextChanged(CharSequence charSequence, int i, int i1, int i2) {
    if(charSequence.length() >= 2 && !edtRUTidUser.getText().toString().equals(newRut)){
        isUnderline = true;
        String rut = edtRUTidUser.getText().toString();
        String lastChar = rut.substring(rut.length() - 1);
        if(!lastChar.equals("-")){
            String cleanRut = rut.replace("-","");
            newRut = cleanRut.substring(0,cleanRut.length()-1) + "-" + lastChar;
            edtRUTidUser.setText(newRut);
        }
    }else if(charSequence.length() < 2){
        isUnderline = false;
    }
    edtRUTidUser.setSelection(edtRUTidUser.getText().toString().length());
}
```
