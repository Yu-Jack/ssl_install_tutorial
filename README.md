# GoDaddy Certificate Install ( Tomcat )

## New Install
[GoDaddy official tutorial](https://tw.godaddy.com/help/tomcat-4x5x6x7x-csr-ssl-5239)

## Replace the Certificate on existing keystore

1.  
    Replace the alias name with new certificate  
    ```
    keytool -import -alias [your_alias_name] -keystore tomcat.keystore -trustcacerts -file 5998qowij1.crt ( This is godday certificate file )
    ```

2.  
    Change the intermed certificate  
    ```
    keytool -delete -alias intermed -keystore tomcat.keystore
    keytool -import -alias intermed -keystore tomcat.keystore -trustcacerts -file gdig2.crt ( This is godday intermed certificate file )
    ```

3.  
    Change the root certificate
    ```
    keytool -delete -alias root -keystore tomcat.keystore
    keytool -import -alias root -keystore tomcat.keystore -trustcacerts -file gd_bundle-g2-g1.crt ( This is godday root certificate file )
    ```

4. Finally, setup the permission of file.  

## Other Useful Command of keytool
[Most Common Java Keytool Commands](https://www.sslshopper.com/article-most-common-java-keytool-keystore-commands.html?jn9ed3e997=3)
```
# Show the keystore detail
keytool -list -v -keystore [your_keystore_file]
```
