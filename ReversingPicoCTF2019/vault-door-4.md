# vault-door-4

## Objetivos
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)


## Solución 
```bash
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,
            'a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}

```

Solución en consola 

 ``` javascript
 String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,) + ['a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e'].join('')

"jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e"
 ```

``` java
import java.util.*;

  

class VaultDoor4 {

public static void main(String args[]) {

VaultDoor4 vaultDoor = new VaultDoor4();

//Scanner scanner = new Scanner(System.in);

//System.out.print("Enter vault password: ");

//String userInput = scanner.next();

// String input = userInput.substring("picoCTF{".length(),userInput.length()-1);

if (vaultDoor.checkPassword()) {

System.out.println("Access granted.");

} else {

System.out.println("Access denied!");

}

}

  

// I made myself dizzy converting all of these numbers into different bases,

// so I just *know* that this vault will be impenetrable. This will make Dr.

// Evil like me better than all of the other minions--especially Minion

// #5620--I just know it!

//

// .:::. .:::.

// :::::::.:::::::

// :::::::::::::::

// ':::::::::::::'

// ':::::::::'

// ':::::'

// ':'

// -Minion #7781

public boolean checkPassword() {

//byte[] passBytes = password.getBytes();

byte[] myBytes = {

106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 ,

0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,

'a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e' ,

};

/*for (int i=0; i<32; i++) {

if (passBytes[i] != myBytes[i]) {

return false;

}

}*/

String flag = new String(myBytes);

System.out.println(flag);

return true;

}

}
```

```shell 
┌──(kali㉿kali)-[~/Downloads]
└─$ javac VaultDoor4.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                                                                                         
┌──(kali㉿kali)-[~/Downloads]
└─$ java VaultDoor4      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e
Access granted
```
## Notas adicionales 

El programa espera una entrada de texto en el formato picoCTF{contraseña} toma solo la contraseña, lo manda a la funcion de validación de password, ahí lo convierte a bytes y lo guarda en un arreglo llamado passBytes, luego se define un arreglo constante con una serie de bytes que comparan caracter con caracter con mi password, 

Para obtener la contraseña, podemos utilizar la consola de firefox con javascript utilizando "fromcharCode" y pegando loas caracteres  y unimos la parte que viene en forma de texto 

La segunda forma es modificando el programa original y deshabilitar partes que no nos interesan 
