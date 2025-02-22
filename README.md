# Documentación de PyCrypter

`pycrypter` es una biblioteca de Python que proporciona varios algoritmos criptográficos para el cifrado y descifrado. Incluye implementaciones de cifrados clásicos como Caesar, Hill y Enigma, así como técnicas de cifrado modernas como DES, ChaCha20, RC4, RC5, RC6, Salsa20, Triple DES y Transposition Cipher. La biblioteca está diseñada para ser fácil de usar y ampliar, lo que la hace adecuada tanto para fines educativos como para aplicaciones prácticas.

## Tabla de contenidos

- [Documentación de PyCrypter](#documentación-de-pycrypter)
  - [Tabla de contenidos](#tabla-de-contenidos)
- [Cifrados](#cifrados)
  - [Binario](#binario)
    - [Métodos](#métodos)
  - [Cifrado César](#cifrado-césar)
    - [Métodos](#métodos-1)
  - [Cifrado ChaCha20](#cifrado-chacha20)
    - [Métodos](#métodos-2)
  - [Cifrado DES](#cifrado-des)
    - [Métodos](#métodos-3)
  - [Máquina Enigma](#máquina-enigma)
    - [Métodos](#métodos-4)
  - [Cifrado Hill](#cifrado-hill)
    - [Métodos](#métodos-5)
  - [Cifrado monoalfabético](#cifrado-monoalfabético)
    - [Métodos](#métodos-6)
  - [Cifrado polialfabético](#cifrado-polialfabético)
    - [Métodos](#métodos-7)
  - [Cifrado RC4](#cifrado-rc4)
    - [Métodos](#métodos-8)
  - [Cifrado RC5](#cifrado-rc5)
    - [Métodos](#métodos-9)
  - [Cifrado RC6](#cifrado-rc6)
    - [Métodos](#métodos-10)
  - [Cifrado Salsa20](#cifrado-salsa20)
    - [Métodos](#métodos-11)
  - [Cifrado de transposición](#cifrado-de-transposición)
    - [Métodos](#métodos-12)
  - [Cifrado Triple DES](#cifrado-triple-des)
    - [Métodos](#métodos-13)
- [Hash](#hash)
  - [Hash MD5](#hash-md5)
    - [Métodos](#métodos-14)
  - [Ejemplos](#ejemplos)
    - [Ejemplo binario](#ejemplo-binario)
    - [Ejemplo de Caesar](#ejemplo-de-caesar)
    - [Ejemplo de ChaCha20](#ejemplo-de-chacha20)
    - [Ejemplo de DES](#ejemplo-de-des)
    - [Ejemplo de máquina Enigma](#ejemplo-de-máquina-enigma)
    - [Ejemplo de Hill](#ejemplo-de-hill)
    - [Ejemplo de cifrado monoalfabético](#ejemplo-de-cifrado-monoalfabético)
    - [Ejemplo polialfabético](#ejemplo-polialfabético)
    - [Ejemplo RC4](#ejemplo-rc4)
    - [Ejemplo RC5](#ejemplo-rc5)
    - [RC6 Cipher](#rc6-cipher)
    - [Salsa20Cipher](#salsa20cipher)
    - [Ejemplo de cifrado de transposición](#ejemplo-de-cifrado-de-transposición)
    - [Ejemplo de cifrado Triple DES](#ejemplo-de-cifrado-triple-des)
    - [Hash MD5](#hash-md5-1)

---

# Cifrados

## Binario

La clase `Binary` proporciona métodos estáticos para convertir texto a representación binaria y viceversa.

### Métodos

- **`text_to_binary(text: str) -> str`**: Convierte una cadena de texto a su representación binaria. Cada carácter se representa como un número binario de 8 bits, separado por espacios.

**Parámetros**:

- `text` (str): El texto a convertir.

**Devuelve**:

- `str`: La representación binaria del texto.

- **`binary_to_text(binary: str) -> str`**: Convierte una cadena binaria nuevamente a texto. La cadena binaria debe estar compuesta por bytes separados por espacios.

**Parámetros**:

- `binary` (str): La cadena binaria a convertir.

**Devuelve**:

- `str`: El texto decodificado.

- **`text_to_binary_file(text: str, file_path: str)`**: Convierte texto a binario y lo guarda en un archivo.

**Parámetros**:

- `text` (str): El texto a convertir.

- `file_path` (str): La ruta del archivo donde se guardará la representación binaria.

- **`binary_file_to_text(file_path: str) -> str`**: Lee un archivo binario y lo convierte nuevamente en texto.

**Parámetros**:

- `file_path` (str): La ruta del archivo que contiene la representación binaria.

**Devuelve**:

- `str`: El texto decodificado.

---

## Cifrado César

La clase `CaesarCipher` implementa el cifrado César clásico, un cifrado de sustitución donde cada letra del texto simple se desplaza un número fijo de posiciones hacia abajo en el alfabeto.

### Métodos

- **`encrypt_text(text: str, shift: int) -> str`**: Cifra un texto utilizando el cifrado César.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `shift` (int): La cantidad de posiciones a las que se debe desplazar cada letra.

**Devuelve**:

- `str`: El texto cifrado.

- **`decrypt_text(text: str, shift: int) -> str`**: Descifra un texto que se cifró con el cifrado César.

**Parámetros**:

- `text` (str): El texto cifrado.

- `shift` (int): La cantidad de posiciones utilizadas para cifrar.

**Devuelve**:

- `str`: El texto descifrado.

- **`encrypt_file(file_path: str, shift: int, output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando el cifrado César y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se va a cifrar.

- `shift` (int): La cantidad de posiciones que se deben desplazar para cada letra.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, shift: int, output_file_path: str = None)`**: Descifra el contenido de un archivo que se cifró con el cifrado César.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `shift` (int): La Número de posiciones utilizadas para cifrar.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado ChaCha20

La clase `ChaCha20Cipher` implementa el cifrado de flujo ChaCha20, un algoritmo de cifrado moderno diseñado por Daniel J. Bernstein. Se utiliza ampliamente en protocolos de comunicación segura como TLS 1.3.

### Métodos

- **`encrypt(text: str, key: bytes, nonce: bytes = None) -> Tuple[bytes, bytes]`**: Cifra un texto utilizando el cifrado ChaCha20.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce (12 bytes, opcional).

**Devuelve**:

- `Tuple[bytes, bytes]`: Los datos cifrados y el nonce utilizado.

- **`decrypt(encrypted_data: bytes, key: bytes, nonce: bytes) -> str`**: Descifra los datos que se cifraron con el cifrado ChaCha20.

**Parámetros**:

- `encrypted_data` (bytes): Los datos cifrados.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce utilizado durante el cifrado.

**Devuelve**:

- `str`: El texto descifrado.

- **`generate_key() -> bytes`**: Genera una clave aleatoria de 32 bytes para ChaCha20.

**Devuelve**:

- `bytes`: Una clave aleatoria de 32 bytes.

- **`encrypt_file(file_path: str, key: bytes, nonce: bytes = None, output_file_path: str = None)`**: Encripta el contenido de un archivo usando ChaCha20 y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `key` (bytes): La clave de encriptación (32 bytes).

- `nonce` (bytes): El nonce (12 bytes, opcional).

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, key: bytes, nonce: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue encriptado con ChaCha20.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce utilizado durante el cifrado.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado DES

La clase `DESCipher` implementa el Estándar de cifrado de datos (DES), un cifrado de bloques de clave simétrica que utiliza una clave de 56 bits.

### Métodos

- **`encrypt_des(text: str, key: bytes) -> bytes`**: Cifra un texto utilizando DES en modo CBC.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado (ajustada a 8 bytes).

**Devuelve**:

- `bytes`: El IV concatenado con el texto cifrado.

- **`decrypt_des(encrypted_text: bytes, key: bytes) -> str`**: Descifra los datos que se cifraron con DES en modo CBC.

**Parámetros**:

- `encrypted_text` (bytes): El IV + el texto cifrado.

- `key` (bytes): La clave de descifrado (ajustada a 8 bytes).

**Devuelve**:

- `str`: El texto descifrado.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando DES y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se cifrará.

- `key` (bytes): La clave de cifrado (ajustada a 8 bytes).

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue cifrado con DES.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de descifrado (ajustada a 8 bytes).

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Máquina Enigma

La clase `EnigmaMachine` simula la máquina Enigma, un dispositivo de cifrado histórico utilizado durante la Segunda Guerra Mundial. Utiliza una serie de rotores para realizar la sustitución polialfabética.

### Métodos

- **`encrypt_char(char: str) -> str`**: Encripta un solo carácter usando la máquina Enigma.

**Parámetros**:

- `char` (str): El carácter a encriptar.

**Devuelve**:

- `str`: El carácter encriptado.

- **`encrypt(text: str) -> str`**: Encripta un texto usando la máquina Enigma.

**Parámetros**:

- `text` (str): El texto a encriptar.

**Devuelve**:

- `str`: El texto encriptado.

- **`encrypt_file(file_path: str, output_file_path: str = None)`**: Encripta el contenido de un archivo usando la máquina Enigma y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue cifrado con la máquina Enigma.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado Hill

La clase `HillCipher` implementa el cifrado Hill, un cifrado de sustitución poligráfica basado en álgebra lineal. usa una matriz como clave para cifrar bloques de letras de texto sin formato.

### Métodos

- **`encrypt_hill(text: str, key_matrix: List[List[int]]) -> Tuple[str, int]`**: cifra un texto utilizando el cifrado Hill.

**Parámetros**:

- `text` (str): el texto a cifrar.

- `key_matrix` (List[List[int]]): la matriz de claves de cifrado.

**Devuelve**:

- `Tuple[str, int]`: el texto cifrado y el recuento de relleno.

- **`decrypt_hill(text: str, key_matrix: List[List[int]], padding_count: int = 0) -> str`**: descifra un texto que se cifró con el cifrado Hill.

**Parámetros**:

- `text` (str): el texto cifrado.

- `key_matrix` (List[List[int]]): La matriz de claves de descifrado.

- `padding_count` (int): La cantidad de caracteres de relleno agregados durante el cifrado.

**Devuelve**:

- `str`: El texto descifrado.

- **`encrypt_file(file_path: str, key_matrix: List[List[int]], output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando el cifrado Hill y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se va a cifrar.

- `key_matrix` (List[List[int]]): La matriz de claves de cifrado.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, key_matrix: List[List[int]], padding_count: int = 0, output_file_path: str = None)`**: Descifra el contenido de un archivo que se cifró con el cifrado Hill.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key_matrix` (List[List[int]]): La matriz de claves de descifrado.

- `padding_count` (int): La cantidad de caracteres de relleno agregados durante el cifrado.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado monoalfabético

La clase `MonoalphabeticCipher` implementa un cifrado de sustitución simple donde cada letra del texto simple se reemplaza por una letra fija diferente del alfabeto.

### Métodos

- **`generate_substitution_alphabet() -> dict`**: Genera un alfabeto de sustitución aleatorio.

**Devuelve**:

- `dict`: Un diccionario que asigna cada letra a su sustitución.

- **`encrypt_monoalphabetic(text: str, substitution_alphabet: dict) -> str`**: Encripta un texto usando el alfabeto de sustitución.

**Parámetros**:

- `text` (str): El texto a encriptar.

- `substitution_alphabet` (dict): El alfabeto de sustitución a usar.

**Devuelve**:

- `str`: El texto encriptado.

- **`decrypt_monoalphabetic(text: str, substitution_alphabet: dict) -> str`**: Desencripta un texto usando el alfabeto de sustitución.

**Parámetros**:

- `text` (str): El texto a desencriptar.

- `substitution_alphabet` (dict): El alfabeto de sustitución utilizado para el cifrado.

**Devuelve**:

- `str`: El texto descifrado.

- **`encrypt_file(file_path: str, substitution_alphabet: dict, output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando el cifrado monoalfabético y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se va a cifrar.

- `substitution_alphabet` (dict): El alfabeto de sustitución que se va a utilizar.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, substitution_alphabet: dict, output_file_path: str = None)`**: descifra el contenido de un archivo que se cifró con el cifrado monoalfabético.

**Parámetros**:

- `file_path` (str): la ruta al archivo cifrado.

- `substitution_alphabet` (dict): el alfabeto de sustitución utilizado para el cifrado.

- `output_file_path` (str): la ruta para guardar el archivo descifrado (opcional).

---

## Cifrado polialfabético

La clase `PolyalphabeticCipher` implementa el cifrado Vigenère, un método para cifrar texto alfabético mediante una forma simple de sustitución polialfabética.

### Métodos

- **`encrypt_polyalphabetic(text: str, key: str) -> str`**: Encripta un texto usando el cifrado Vigenère.

**Parámetros**:

- `text` (str): El texto a encriptar.

- `key` (str): La clave de encriptación.

**Devuelve**:

- `str`: El texto encriptado.

- **`decrypt_polyalphabetic(text: str, key: str) -> str`**: Descifra un texto que fue encriptado con el cifrado Vigenère.

**Parámetros**:

- `text` (str): El texto encriptado.

- `key` (str): La clave de encriptación usada.

**Devuelve**:

- `str`: El texto desencriptado.

- **`encrypt_file(file_path: str, key: str, output_file_path: str = None)`**: Encripta el contenido de un archivo usando el cifrado Vigenère y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `key` (str): La clave de encriptación.

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, key: str, output_file_path: str = None)`**: Desencripta el contenido de un archivo que fue encriptado con el cifrado Vigenère.

**Parámetros**:

- `file_path` (str): La ruta al archivo encriptado.

- `key` (str): La clave de encriptación usada .

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado RC4

La clase `RC4Cipher` implementa el cifrado de flujo RC4, un algoritmo de cifrado ampliamente utilizado pero que ahora se considera inseguro.

### Métodos

- **`encrypt_rc4(text: str, key: bytes) -> bytes`**: Cifra un texto utilizando el cifrado RC4.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado.

**Devuelve**:

- `bytes`: Los datos cifrados.

- **`decrypt_rc4(encrypted_text: bytes, key: bytes) -> str`**: Descifra los datos que se cifraron con el cifrado RC4.

**Parámetros**:

- `encrypted_text` (bytes): Los datos cifrados.

- `key` (bytes): La clave de cifrado utilizada.

**Devuelve**:

- `str`: El texto descifrado.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando el cifrado RC4 y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se va a cifrar.

- `key` (bytes): La clave de cifrado.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que se cifró con el cifrado RC4.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de cifrado utilizada.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado RC5

La clase `RC5Cipher` implementa el cifrado de bloques RC5, un algoritmo de clave simétrica diseñado por Ronald Rivest.

### Métodos

- **`encrypt_rc5(text: str, key: bytes) -> bytes`**: Cifra un texto utilizando el cifrado RC5.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado.

**Devuelve**:

- `bytes`: Los datos cifrados.

- **`decrypt_rc5(encrypted_data: bytes, key: bytes) -> str`**: Descifra los datos que se cifraron con el cifrado RC5.

**Parámetros**:

- `encrypted_data` (bytes): Los datos cifrados.

- `key` (bytes): La clave de cifrado utilizada.

**Devuelve**:

- `str`: El texto descifrado.

- **`generate_key(size: int = 16) -> bytes`**: Genera una clave aleatoria para RC5.

**Parámetros**:

- `size` (int): El tamaño de la clave en bytes (el valor predeterminado es 16).

**Devuelve**:

- `bytes`: Una clave aleatoria.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encripta el contenido de un archivo usando el cifrado RC5 y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `key` (bytes): La clave de encriptación.

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Desencripta el contenido de un archivo que fue encriptado con el cifrado RC5.

**Parámetros**:

- `file_path` (str): La ruta al archivo encriptado.

- `key` (bytes): La clave de encriptación usada.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado RC6

La clase `RC6Cipher` implementa el cifrado de bloques RC6, una versión más avanzada de RC5.

### Métodos

- **`encrypt_rc6(text: str, key: bytes) -> bytes`**: Cifra un texto utilizando el cifrado RC6.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado.

**Devuelve**:

- `bytes`: Los datos cifrados.

- **`decrypt_rc6(encrypted_data: bytes, key: bytes) -> str`**: Descifra los datos que se cifraron con el cifrado RC6.

**Parámetros**:

- `encrypted_data` (bytes): Los datos cifrados.

- `key` (bytes): La clave de cifrado utilizada.

**Devuelve**:

- `str`: El texto descifrado.

- **`generate_key(size: int = 16) -> bytes`**: Genera una clave aleatoria para RC6.

**Parámetros**:

- `size` (int): El tamaño de la clave en bytes (el valor predeterminado es 16).

**Devuelve**:

- `bytes`: Una clave aleatoria.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Cifra el contenido de un archivo utilizando el cifrado RC6 y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo que se va a cifrar.

- `key` (bytes): La clave de cifrado.

- `output_file_path` (str): La ruta para guardar el archivo cifrado (opcional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que se cifró con el cifrado RC6.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de cifrado utilizada.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado Salsa20

La clase `Salsa20Cipher` implementa el cifrado de flujo Salsa20, un algoritmo de cifrado moderno diseñado por Daniel J. Bernstein.

### Métodos

- **`encrypt(text: str, key: bytes, nonce: bytes = None) -> Tuple[bytes, bytes]`**: Encripta un texto usando el código de cifrado Salsa20 ella.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce (8 bytes, opcional).

**Devuelve**:

- `Tuple[bytes, bytes]`: Los datos cifrados y el nonce utilizado.

- **`decrypt(encrypted_data: bytes, key: bytes, nonce: bytes) -> str`**: Descifra los datos que se cifraron con el cifrado Salsa20.

**Parámetros**:

- `encrypted_data` (bytes): Los datos cifrados.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce utilizado durante el cifrado.

**Devuelve**:

- `str`: El texto descifrado.

- **`generate_key() -> bytes`**: Genera una clave aleatoria de 32 bytes para Salsa20.

**Devuelve**:

- `bytes`: Una clave aleatoria de 32 bytes.

- **`encrypt_file(file_path: str, key: bytes, nonce: bytes = None, output_file_path: str = None)`**: Encripta el contenido de un archivo usando Salsa20 y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `key` (bytes): La clave de encriptación (32 bytes).

- `nonce` (bytes): El nonce (8 bytes, opcional).

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, key: bytes, nonce: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue cifrado con Salsa20.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de cifrado (32 bytes).

- `nonce` (bytes): El nonce utilizado durante el cifrado.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

## Cifrado de transposición

La clase `TranspositionCipher` implementa el cifrado Rail Fence, una forma de cifrado de transposición que reorganiza las letras del texto simple escribiéndolas en un patrón en zigzag a lo largo de una serie de rieles.

### Métodos

- **`encrypt_transposition(text: str, rails: int) -> str`**: Encripta un texto usando el cifrado Rail Fence.

**Parámetros**:

- `text` (str): El texto a encriptar.

- `rails` (int): La cantidad de rieles a usar (debe ser >= 2).

**Devuelve**:

- `str`: El texto encriptado.

- **`decrypt_transposition(text: str, rails: int) -> str`**: Descifra un texto que fue encriptado usando el cifrado Rail Fence.

**Parámetros**:

- `text` (str): El texto encriptado.

- `rails` (int): La cantidad de rieles usados ​​en el cifrado (debe ser >= 2).

**Devuelve**:

- `str`: El texto desencriptado.

- **`encrypt_file(file_path: str, rails: int, output_file_path: str = None)`**: Encripta el contenido de un archivo usando el cifrado Rail Fence y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `rails` (int): La cantidad de rieles a usar.

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, rails: int, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue encriptado con el cifrado Rail Fence.

**Parámetros**:

- `file_path` (str): La ruta al archivo encriptado.

- `rails` (int): La cantidad de rieles usados ​​en el cifrado.

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

---

## Cifrado Triple DES

La clase `TripleDESCipher` implementa el algoritmo de cifrado Triple DES (3DES), que aplica el algoritmo DES tres veces a cada bloque de datos utilizando dos o tres claves diferentes, lo que proporciona un mayor nivel de seguridad que el DES estándar.

### Métodos

- **`generate_key() -> bytes`**: Genera una clave aleatoria válida de 24 bytes para Triple DES.

**Devuelve**:

- `bytes`: Una clave de 24 bytes adecuada para Triple DES.

- **`encrypt_des3(text: str, key: bytes) -> bytes`**: Cifra un texto utilizando Triple DES en modo CBC.

**Parámetros**:

- `text` (str): El texto a cifrar.

- `key` (bytes): La clave de cifrado (16 o 24 bytes).

**Devuelve**:

- `bytes`: El IV concatenado con el texto cifrado.

- **`decrypt_des3(encrypted_data: bytes, key: bytes) -> str`**: Descifra los datos que se cifraron con Triple DES.

**Parámetros**:

- `encrypted_data` (bytes): El IV + los datos cifrados.

- `key` (bytes): La clave de descifrado (16 o 24 bytes).

**Devuelve**:

- `str`: El texto descifrado.

- **`validate_key(key: bytes) -> bool`**: Valida si una clave es adecuada para su uso con Triple DES.

**Parámetros**:

- `key` (bytes): La clave a validar.

**Devuelve**:

- `bool`: `True` si la clave es válida, `False` en caso contrario.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encripta el contenido de un archivo usando Triple DES y lo guarda en otro archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo a encriptar.

- `key` (bytes): La clave de encriptación (16 o 24 bytes).

- `output_file_path` (str): La ruta para guardar el archivo encriptado (opcional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Descifra el contenido de un archivo que fue encriptaypted con Triple DES.

**Parámetros**:

- `file_path` (str): La ruta al archivo cifrado.

- `key` (bytes): La clave de descifrado (16 o 24 bytes).

- `output_file_path` (str): La ruta para guardar el archivo descifrado (opcional).

# Hash

## Hash MD5

La clase `MD5Hash` implementa el algoritmo de hash MD5, que produce un valor hash de 128 bits. Aunque MD5 ya no se considera seguro para fines criptográficos, todavía se usa ampliamente para la verificación de la integridad de los datos.

### Métodos

- **`hash(message: str) -> str`**: Calcula el hash MD5 de un mensaje.

**Parámetros**:

- `message` (str): El mensaje al que se aplicará el hash.

**Devuelve**:

- `str`: El hash MD5 como una cadena hexadecimal.

- **`hash_file(file_path: str) -> str`**: Calcula el hash MD5 de un archivo.

**Parámetros**:

- `file_path` (str): La ruta al archivo al que se aplicará el hash.

**Devuelve**:

- `str`: El hash MD5 del archivo como una cadena hexadecimal.

---

## Ejemplos

### Ejemplo binario

```python

from pycrypter.Ciphers import Binary

binary_text = Binary.text_to_binary("Hola")

print(binary_text) # Salida: "01001000 01100101 01101100 01101100 01101111"

text = Binary.binary_to_text("01001000 01100101 01101100 01101100 01101111")

print(text) # Salida: "Hola"

```

### Ejemplo de Caesar

```python

from pycrypter.Ciphers import CaesarCipher

encrypted = CaesarCipher.encrypt_text("Hola", 3)

print(encrypted) # Salida: "Khoor"

decrypted = CaesarCipher.decrypt_text("Khoor", 3)

print(decrypted) # Salida: "Hola"

```

### Ejemplo de ChaCha20

```python

from pycrypter.Ciphers import ChaCha20Cipher

key = ChaCha20Cipher.generate_key()

encrypted, nonce = ChaCha20Cipher.encrypt("Hola", key)

print(encrypted) # Salida: bytes cifrados

decrypted = ChaCha20Cipher.decrypt(encrypted, key, nonce)

print(decrypted) # Salida: "Hola"

```

### Ejemplo de DES

```python

from pycrypter.Cipher import DESCipher

key = b'mykey123'

encrypted = DESCipher.encrypt_des("Hola", clave)

print(encrypted) # Salida: Bytes encriptados

decrypted = DESCipher.decrypt_des(encrypted, clave)

print(decrypted) # Salida: "Hola"

```

### Ejemplo de máquina Enigma

```python

from pycrypter.Ciphers import EnigmaMachine

rotor_configs = [

{'cableado': 'EKMFLGDQVZNTOWYHXUSPAIBRCJ', 'muesca': 'Q'}, # Rotor I

{'cableado': 'AJDKSIRUXBLHWTMCQGZNPYFVOE', 'muesca': 'E'}, # Rotor II

{'cableado': 'BDFHJLCPRTXVZNYEIWGAKMUSQO', 'muesca': 'V'} # Rotor III

]

reflector = {'A': 'Y', 'B': 'R', 'C': 'U', 'D': 'H', 'E': 'Q', 'F': 'S', 'G': 'L',

'H': 'D', 'I': 'P', 'J': 'X', 'K': 'N', 'L': 'G', 'M': 'O', 'N': 'K',

'O': 'M', 'P': 'I', 'Q': 'E', 'R': 'B', 'S': 'F', 'T': 'Z', 'U': 'C',

'V': 'W', 'W': 'V', 'X': 'J', 'Y': 'A', 'Z': 'T'}

enigma = EnigmaMachine(rotor_configs, reflector, [1, 1, 1], ['A', 'A', 'A'])

encriptado = enigma.encrypt("HOLA")

print(encriptado) # Salida: Texto encriptado

```

### Ejemplo de Hill

```python

from pycrypter import HillCipher

key_matrix = [[6, 24, 1], [13, 16, 10], [20, 17, 15]]

encriptado, relleno = HillCipher.encrypt_hill("HOLA", key_matrix)

print(encriptado) # Salida: Texto encriptado

desencriptado = HillCipher.decrypt_hill(encriptado, key_matrix, relleno)

print(desencriptado) # Salida: "HOLA"

```

### Ejemplo de cifrado monoalfabético

```python

from pycrypter.Ciphers import MonoalphabeticCipher

substitution_alphabet = MonoalphabeticCipher.generate_substitution_alphabet()

encrypted = MonoalphabeticCipher.encrypt_monoalphabetic("Hola", substitution_alphabet)

print(encrypted) # Salida: Texto cifrado

decrypted = MonoalphabeticCipher.decrypt_monoalphabetic(encrypted, substitution_alphabet)

print(decrypted) # Salida: "Hola

```

### Ejemplo polialfabético

```python

from pycrypter.Ciphers import PolyalphabeticCipher

encrypted = PolyalphabeticCipher.encrypt_polyalphabetic("Hola", "clave")

print(encrypted) # Salida: Texto cifrado

decrypted = PolyalphabeticCipher.decrypt_polyalphabetic(encrypted, "clave")

print(decrypted) # Salida: "Hola"

```

### Ejemplo RC4

```python

from pycrypter.Ciphers import RC4Cipher

clave = b'mykey123'

encrypted = RC4Cipher.encrypt_rc4("Hola", clave)

print(encrypted) # Salida: Bytes cifrados

decrypted = RC4Cipher.decrypt_rc4(encrypted, clave)

print(decrypted) # Salida: "Hola"

```

### Ejemplo RC5

```python

from pycrypter.Ciphers import RC5Cipher

key = RC5Cipher.generate_key()

encrypted = RC5Cipher.encrypt_rc5("Hola", clave)

print(encrypted) # Salida: Bytes cifrados

decrypted = RC5Cipher.decrypt_rc5(encrypted, clave)

print(descrypted) # Salida: "Hola"

```

### RC6 Cipher

```python

from pycrypter.Ciphers import RC6Cipher

key = RC6Cipher.generate_key()

encrypted = RC6Cipher.encrypt_rc6("Hola", clave)

print(encrypted) # Salida: Bytes cifrados

decrypted = RC6Cipher.decrypt_rc6(encrypted, clave)

print(descrypted) # Salida: "Hola"

```

### Salsa20Cipher

```python

from pycrypter.Ciphers import Salsa20Cipher

key = Salsa20Cipher.generate_key()

encrypted, nonce = Salsa20Cipher.encrypt("Hola", clave)

print(encrypted) # Salida: Bytes encriptados

decrypted = Salsa20Cipher.decrypt(encrypted, key, nonce)

print(decrypted) # Salida: "Hola"

```

### Ejemplo de cifrado de transposición

```python

from pycrypter.Ciphers import TranspositionCipher

encrypted = TranspositionCipher.encrypt_transposition("HELLOWORLD", 3)

print(encrypted) # Salida: "HOLELWRDLO"

decrypted = TranspositionCipher.decrypt_transposition("HOLELWRDLO", 3)

print(descifrado) # Salida: "HELLOWORLD"

```

### Ejemplo de cifrado Triple DES

```python

from pycrypter.Ciphers import TripleDESCipher

key = TripleDESCipher.generate_key()

encrypted = TripleDESCipher.encrypt_des3("Hola", clave)

print(encrypted) # Salida: Bytes cifrados

descifrado = TripleDESCipher.decrypt_des3(encrypted, clave)

print(descifrado) # Salida: "Hola"

```

### Hash MD5

```python

from pycrypter import MD5Hash

# Hash de un mensaje

message_hash = MD5Hash.hash("¡Hola, mundo!")

print(message_hash) # Salida: hash MD5 de "¡Hola, mundo!"

# Convertir un archivo en hash

file_hash = MD5Hash.hash_file("example.txt")

print(file_hash) # Salida: hash MD5 del contenido del archivo

```