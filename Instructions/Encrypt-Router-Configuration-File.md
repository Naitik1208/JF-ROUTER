# Encrypt Configuration File 

*Disclaimer: - This is Only for educational purposes, No one is responsible for any type of damage.*
1.They keyguesser.py window will have a key when it decrypts your config like this in image <img width="428" height="91" alt="image" src="https://github.com/user-attachments/assets/233eae55-3d60-4170-beec-a33ed552d60b" />
You have to copy one after Success the hex one not upper one and make a file key.txt in same folder.
2.  Open Terminal or Command Prompt.
3. Use this command to re-encrypt the text configuration file with your respective `key.txt` :- 
`openssl aes-128-cbc -kfile "<path to the key file>" -in "RSTXXXXXXX_JCXXXXX.txt" -out "RSTXXXXXXX_JCXXXXX_MODIFIED.enc"`
4. In your Router WEB-UI Page (`http://192.168.29.1`), go to `Administrator --> Maintenance`.
5. Select and restore the `RSTXXXXXXX_JCXXXXX_MODIFIED.enc` file.
