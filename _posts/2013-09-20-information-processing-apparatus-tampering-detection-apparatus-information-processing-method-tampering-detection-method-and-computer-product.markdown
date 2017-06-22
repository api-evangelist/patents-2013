---

title: Information processing apparatus, tampering detection apparatus, information processing method, tampering detection method, and computer product
abstract: An information processing apparatus includes a processor configured to identify a data length that is longer than a data length of plain text data and that is a multiple of a predetermined block length; calculate a data length difference of the data length of the plain text and the data length; generate a first code that indicates the calculated data length difference; generate a second code that is calculated from the plain text data and is of a data length that is within a remaining data length acquired by subtracting a data length of the generated first code from the data length difference; create padding that includes the generated second code, has the first code at an end, and is of a length equivalent to the data length difference; concatenate the created padding to an end of the plain text data to generate concatenated data; and output the concatenated data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09071420&OS=09071420&RS=09071420
owner: FUJITSU LIMITED
number: 09071420
owner_city: Kawasaki
owner_country: JP
publication_date: 20130920
---
This application is a continuation application of International Application PCT JP2011 057480 filed on Mar. 25 2011 and designating the U.S. the entire contents of which are incorporated herein by reference.

The embodiment discussed herein is related to an information processing apparatus a tampering detection apparatus an information processing method a tampering detection method and a computer product that use block cipher.

In the information society of today ensuring safe handling of information is important. To ensure the security of information encryption technology for keeping information confidential and technology for detecting tampering of information are required.

Encryption technology includes encryption using a common key system hereinafter referred to as common key encryption and encryption using a public key system hereinafter referred to as public key encryption . The common key encryption advantageously has faster processing speed and enables compact implementation as compared to the public key encryption. Therefore the common key encryption is used when an encryption function is added to small devices such as portable telephones and IC cards.

In block cipher which is one type of common key encryption data to be encrypted hereinafter referred to as plain text is divided into block units for encryption. Since the encryption is performed on the basis of a block unit the data length of plain text must be a multiple of the data length of a block hereinafter referred to as a block length .

Therefore according to one technique if the data length of plain text is not a multiple of the block length padding is concatenated to the plain text to thereby process the plain text into a data length that is a multiple of the block length. The padding to be concatenated includes information necessary for removing the padding at the time of decryption. For example the padding includes information indicating the data length of the padding hereinafter referred to as a padding length .

A technique of detecting tampering of information includes for example a technique of determining whether the contents of padding in plain text decrypted from a series of blocks encrypted for each block length hereinafter referred to as encrypted blocks conform to a padding rule. As a result if the contents of the padding in decrypted plain text have changed consequent to tampering of the encrypted blocks the padding violates the padding rule and therefore the tampering can be detected.

In a technique of detecting tampering of information for example a CRC for identifying plain text is concatenated to the plain text at the time of encryption. The plain text concatenated with the CRC is processed into a data length that is a multiple of the block length by further concatenating padding before encryption. At the time of decryption a CRC for identifying decrypted plain text is compared with the CRC added to the decrypted plain text in this technique. As a result if the plain text has changed consequent to tampering of the encrypted blocks the CRC of the decrypted plain text is different from the CRC added to the decrypted plain text and therefore the tampering can be detected see e.g. Japanese Laid Open Patent Publication No. 2006 220747 .

However the technique of detecting tampering based on the padding rule has a problem in that if a block other than a block to which padding is added i.e. the last block of encrypted text is subject to tampering the tampering cannot be detected.

The technique according to Japanese Laid Open Patent Publication No. 2006 220747 can be used only for a fixed plain text data length and gives no consideration to a case of an arbitrary data length and if the technique is used for an arbitrary data length a CRC must newly be concatenated and a data amount is problematically increased. Therefore it is problematic that the technique according to Japanese Laid Open Patent Publication No. 2006 220747 is not applicable in an embedded environment with tight resources since an area for concatenating a CRC cannot be prepared.

According to an aspect of an embodiment an information processing apparatus includes a processor configured to identify a data length that is longer than a data length of plain text data and that is a multiple of a predetermined block length calculate a data length difference of the data length of the plain text and the identified data length generate a first code that indicates the calculated data length difference generate a second code that is calculated from the plain text data and is of a data length that is within a remaining data length acquired by subtracting a data length of the generated first code from the data length difference create padding that includes the generated second code has the first code at an end and is of a length equivalent to the data length difference concatenate the created padding to an end of the plain text data to generate concatenated data and output the concatenated data.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention.

An embodiment of an information processing apparatus a tampering detection apparatus an information processing method a tampering detection method an information processing program and a tampering detection program will be described in detail with reference to the accompanying drawings. In the following description it is assumed that the information processing apparatus is different from the tampering detection apparatus for simplicity of description. However the information processing apparatus may also have the function of the tampering detection apparatus and the tampering detection apparatus may also have the function of the information processing apparatus.

The information processing apparatus and the tampering detection apparatus are connected to a network . An attacker s computer is connected to the network . The information processing apparatus and the tampering detection apparatus have an encryption key hereinafter referred to as a common key that can be used for encryption and decryption.

The information processing apparatus encrypts the plain text PT by block cipher using the common key. In the block cipher the information processing apparatus must concatenate padding pd to the plain text PT that is to be encrypted so as to process the plain text PT into a data length that can be divided into block units i.e. a data length that is a multiple of a block length bl . The plain text PT concatenated with the padding pd will hereinafter be referred to as a concatenated text APT .

The padding pd concatenated to the plain text PT includes a data length pl of the padding pd hereinafter referred to as a padding length necessary for removing the padding pd at the tampering detection apparatus . The padding pd concatenated to the plain text PT includes data used for detection of tampering in the tampering detection apparatus .

The tampering detection apparatus decrypts blocks that are received via the network and have been encrypted by block cipher using the common key. The tampering detection apparatus detects the presence or absence of tampering based on the decrypted data.

Details of detection of tampering in the tampering detection apparatus will be described hereinafter by taking as an example a case where the information processing apparatus encrypts and transmits to the tampering detection apparatus plain text PT having a data length of 44 bytes . However it is assumed that the block length bl is 16 bytes .

 1 The information processing apparatus checks the data length of the plain text PT that is to be transmitted and calculates the padding length pl of the padding pd to be concatenated to the plain text PT. For example since the plain text PT has a data length of 44 bytes the data length is short of 48 bytes i.e. triple data length of the block length bl 16 bytes by 4 bytes . Therefore the information processing apparatus calculates the padding length pl as 4 bytes .

 2 The information processing apparatus processes the plain text PT into a concatenated text APT having a data length of 48 bytes which is three times longer than the block length bl 16 bytes for encryption by block cipher. For example the information processing apparatus concatenates the padding pd of the calculated padding length pl 4 bytes to the end of the plain text PT to create the concatenated text APT having a data length equal to a multiple of the block length bl.

In the padding pd the information of the padding length pl of the padding pd necessary for the tampering detection apparatus to remove the padding pd is stored in an area at the end of the padding pd.

The area at the end of the padding pd storing the information of the padding length pl hereinafter referred as a padding length area has a data length ll hereinafter referred to as a padding length area length ll that is a fixed length and that is a data length capable of indicting the longest padding length pl capable of being concatenated to the plain text PT. For example if the block length is 16 bytes the maximum length of the padding pd capable of being concatenated to the plain text PT is 16 bytes and therefore the padding length area length ll is 4 bits which can indicate 16.

For example 04040404 is employed as the padding pd in this case based on the padding method described in pkcs 7. However 04040404 is in hexadecimal. As a result the tampering detection apparatus can determine that the padding length pl is 4 bytes by reference to 4 indicated by the padding length area corresponding to the last 4 bits of the padding pd.

 3 The information processing apparatus calculates a data length cl hereinafter referred to as storage area length of an area hereinafter referred to as a storage area in the padding pd storing a code calculated from the plain text PT. For example a CRC of the plain text PT can be employed as the code calculated from the plain text PT.

For example the information processing apparatus defines an area in the padding pd exclusive of the padding length area as the storage area of the CRC. Therefore the storage area length cl is 28 bits obtained by subtracting the padding length area length ll 4 bits from the padding length pl 4 bytes .

 4 The information processing apparatus calculates from the plain text PT a CRC having a data length that is the same as the calculated storage area length cl. Therefore the information processing apparatus calculates a 28 bit CRC from the plain text PT.

 5 The information processing apparatus stores the calculated bit CRC into the storage area in the padding pd. As a result the information processing apparatus processes the padding pd in the concatenated text APT into the padding pd that includes the padding length pl in the padding length area at the end and that includes the calculated CRC in the storage area.

 6 The information processing apparatus divides the concatenated text APT by the block length bl 16 bytes . Since the data length of the concatenated text APT is 48 bytes in this example the concatenated text APT is divided into three blocks. The resulting blocks are referred to as blocks B to B sequentially from the head block.

 7 The information processing apparatus encrypts by block cipher and transmits the blocks B to B to the tampering detection apparatus . The blocks B to B encrypted by block cipher are referred to as encrypted blocks C to C respectively.

 8 It is assumed that the encrypted blocks C to C transmitted by the information processing apparatus are captured by the attacker s computer and a portion of the encrypted block C is subject to tampering.

 9 The tampering detection apparatus receives the encrypted blocks C to C. The tampering detection apparatus decrypts blocks from the received encrypted blocks C to C. The tampering detection apparatus concatenates the decrypted blocks to create a concatenated text APT .

However since the encrypted block C has been subject to tampering the concatenated text APT created by the tampering detection apparatus based on the encrypted block C is data different from the concatenated text APT in the information processing apparatus .

 10 the tampering detection apparatus refers to 4 indicated by the padding length area at the end of the concatenated text APT to identify that the padding length pl is 4 bytes and removes 4 bytes of the padding pd from the end of the concatenated text APT to create the plain text PT . However consequent to the tampering of the encrypted block C the plain text PT created by the tampering detection apparatus is data that is different from the plain text PT at the information processing apparatus .

 11 The tampering detection apparatus calculates code that is calculated from the plain text PT so that the code has the same data length as the storage area length cl. Specifically the tampering detection apparatus identifies that the storage area length cl is 28 bits from the padding length pl 4 bytes and the padding length area length ll 4 bits . The tampering detection apparatus calculates a 28 bit CRC from the plain text PT . Since the plain text PT is data that is different from the plain text PT the calculated CRC is data that is different from the CRC at the information processing apparatus .

 12 The tampering detection apparatus extracts the CRC of the plain text PT from the identified storage area of 28 bits . The tampering detection apparatus determines whether the calculated CRC and the CRC extracted from the padding pd coincide. The tampering detection apparatus outputs a determination result.

Specifically if the CRC and the CRC are data that are different from each other the tampering detection apparatus can determine that the plain text PT is data that is different from the plain text PT at the information processing apparatus and outputs that tampering has occurred. If the CRC and the CRC are the same data the tampering detection apparatus can determine that the plain text PT has not changed from the plain text PT at the information processing apparatus and outputs that no tampering has occurred.

As described above the information processing apparatus stores the code calculated from the plain text PT into the padding pd. The tampering detection apparatus determines whether the code calculated from the entire decrypted plain text PT and the code calculated from the plain text PT stored in the padding pd coincide. As a result the tampering detection apparatus can detect tampering regardless of which portion of the plain text PT is changed by the tampering.

The information processing apparatus calculates the padding length pl of the padding to be concatenated to the plain text PT before calculating the storage area length cl of the code calculated from the plain text PT to be within a range of the calculated padding length pl. The information processing apparatus creates the code calculated from the plain text PT such that the code has a length equal to or less than the same data length as the calculated storage area length cl and stores the code into the storage area. As a result the data length of the concatenated text APT can be prevented from increasing and the amount of resources used can be reduced.

The information processing apparatus ensures the padding length area when calculating the storage area. As a result based on the data length indicated by the code of the padding length area at the end the tampering detection apparatus can remove the padding pd from the concatenated text APT for which no tampering is detected and acquire plain text PT that is the same as the plain text PT at the information processing apparatus .

As depicted in the information processing apparatus or the tampering detection apparatus includes a central processing unit CPU read only memory ROM random access memory RAM a hard disk drive HDD an encryption circuit an interface I F a display and a keyboard respectively connected by a bus .

The CPU governs overall control of the information processing apparatus or the tampering detection apparatus . The ROM stores programs such as a boot program. The ROM further stores an application programming interface API . The RAM is used as a work area of the CPU . The HDD is a driver device that under the control of the CPU controls the reading and writing of data with respect to an internal hard disk. The encryption circuit encrypts and decrypts data.

The I F is connected to the network such as a local area network LAN a wide area network WAN and the Internet through a communication line and is connected to other apparatuses through the network . The I F administers an internal interface with the network and controls the input and output of data with respect to external apparatuses. For example a modem or a LAN adaptor may be employed as the I F .

The display displays for example data such as text images functional information etc. in addition to a cursor icons and or tool boxes. A cathode ray tube CRT a thin film transistor TFT liquid crystal display a plasma display etc. may be employed as the display . The keyboard includes for example keys for inputting letters numerals and various instructions and performs the input of data. Alternatively a touch panel type input pad or numeric keypad etc. may be adopted. Nonetheless configuration is not limited hereto and may omit the HDD the encryption circuit and the keyboard .

Functions of the information processing apparatus and the tampering detection apparatus will be described with reference to . However a single apparatus may have both the function of the information processing apparatus and the function of the tampering detection apparatus .

An example of a functional configuration of the information processing apparatus will be described with reference to .

The identifying unit has a function of identifying a data length that is longer than the data length of plain text data and that is a multiple of a predetermined block length bl. Plain text data is data that is to be encrypted by block cipher and corresponds to the plain text PT described above. The predetermined block length bl is the data length of one block serving as a unit of division prescribed by block cipher and is the block length bl 16 bytes described above for example.

For example the identifying unit identifies the shortest data length among a group of data lengths that are longer than the data length of the plain text data and that are multiples of the predetermined block length bl. Thus the identifying unit determines how many blocks the plain text PT must be divided into at minimum to enable encryption and calculates a data length in the case of the smallest block number required for encryption. For example when the block length bl is 16 bytes and the plain text PT has 44 bytes the identifying unit identifies a data length of 48 bytes which is three times longer than the block length bl because encryption can be performed if the plain text PT is divided into three blocks at minimum.

As a result the identifying unit can identify a data length that is a multiple of the block length bl as the data length of the concatenated text APT based on how many blocks the plain text PT must be divided into at minimum to enable the block encryption. Since the identifying unit identifies the data length of the concatenated text APT a limitation can be imposed on the data length of the concatenated text APT to be created.

The calculating unit has a function of calculating a data length difference of the data length of the plain text data and the data length identified by the identifying unit . The data length difference is a data length used as the padding length pl. For example when the plain text PT has 44 bytes and the data length identified by the identifying unit is 48 bytes the calculating unit calculates the data length difference of 4 bytes used as the padding length pl. As a result the calculating unit can calculate the padding length pl.

The first generating unit has a function of generating a first code indicating the differential data length calculated by the calculating unit . The first code is a binary code indicating the data length difference.

For example the first generating unit generates the first code which indicates the data length difference such that the first code has the shortest data length capable of indicating the predetermined block length bl. The shortest data length capable of indicating the predetermined block length bl is the shortest data length necessary for indicating the block length bl that is the longest data length usable as the padding length pl.

For example when the block length bl is 16 bytes and the data length difference is 4 bytes the first generating unit uses the shortest data length of 4 bits capable of indicating 16 to create the first code indicating the data length difference of 4 bytes . Therefore the first generating unit generates the code 4 in hexadecimal 0100 in binary indicating the data length difference of 4 bytes .

As a result the first generating unit can generate code indicating the padding length pl necessary for removing the padding pd in the tampering detection apparatus .

The second generating unit has a function of generating a second code that is calculated based on plain text data and is of a data length that is within a remaining data length acquired by subtracting the data length of the first code generated by the first generating unit from the data length difference. The second code is a code calculated from the plain text PT and is for example a cyclic redundancy check code CRC calculated by a cyclic redundancy check code generation function or a hash value calculated by a hash function from the plain text PT or parity code calculated from the plain text PT. The data length of the first code is the padding length area length ll described above.

For example the second generating unit has a function of generating the second code that is calculated from the plain text data and is of the remaining data length which is acquired by subtracting the data length of the first code from the data length difference. For example when the padding length pl is 4 bytes and the padding length area length ll is 4 bits the remaining data length is 28 bits and therefore the second generating unit uses 28 bits to generate a CRC from the plain text PT.

For example an API stored in the ROM is used in calculation of the CRC. Multiple APIs calculating respective CRCs of multiple data lengths may be stored in the ROM and the APIs may selectively be used for calculating the CRC depending on the data length of the CRC to be calculated. The ROM may store alone an API that calculates the CRC of the longest data length among calculable CRCs and a portion of the calculated CRC may be extracted depending on the data length necessary.

As a result the second generating unit can generate code that is calculated from the plain text PT and used as an index for detection of tampering in the tampering detection apparatus such that the code has the storage area length cl.

The creating unit has a function of creating padding that includes the second code generated by the second generating unit has the first code at the tail end and is of a length equivalent to the data length difference. For example the creating unit creates padding having the first code at the tail end and the second code at the head.

For example the creating unit creates padding ending with the first code and starting with the second code. For example the creating unit creates the padding pd ending with the code indicating the padding length pl and starting with the CRC calculated from the plain text PT such that the padding pd has the calculated padding length pl. When the padding length pl is 7 bytes and the CRC is 32 bit 63350373 the padding pd is 7 byte 63350373070707 ending with 7 indicating the padding length pl and starting with 63350373 . The padding pd is in hexadecimal.

When the padding length pl is 4 bytes and the CRC is 28 bit 3F459A1 the padding pd is 3F459A14 having a data length of 4 bytes ending with 4 indicating the padding length pl and starting with 3F459A1 . The padding pd is in hexadecimal.

For example the creating unit creates padding of the data length difference and having the first code at the end and the second code made adjacent to the beginning of the first code. For example the creating unit creates the padding pd having the code indicating the padding length pl at the end and the CRC calculated from the plain text PT made adjacent to the beginning of the code indicating the padding length pl such that the padding pd has the calculated padding length pl. It is assumed that the padding length pl is 7 bytes and that the CRC is 32 bit 63350373 . In this case the padding pd is 7 byte 07070633503737 having 7 indicating the padding length pl at the end and 63350373 made adjacent to the beginning of the code indicating the padding length pl. The padding pd is in hexadecimal.

The creating unit may store code corresponding to the padding length pl and generated by the third generating unit into an area other than the padding length area and the storage area.

As a result the creating unit can create the padding pd to include the padding length necessary for removing the padding pd in the tampering detection apparatus and the code calculated from the plain text PT used as an index for detection of tampering. The creating unit can further create padding that includes the code generated by the third generating unit and used as an index for determining whether the padding length pl is correct at the tampering detection apparatus .

The concatenating unit has a function of concatenating the padding created by the creating unit to the tail end of the plain text data to generate concatenated data. The concatenated data corresponds to the concatenated text APT described above. For example the concatenating unit concatenates the padding pd to the end of the plain text PT to generate the concatenated text APT of a data length that is a multiple of the block length bl. As a result the concatenating unit can create concatenated text APT having a data length that is a multiple of the block length bl and capable of being encrypted by block cipher.

The output unit has a function of outputting the concatenated data acquired by the concatenating unit . For example the output unit causes the I F to transmit the concatenated text APT via the network to another apparatus. The output unit outputs the concatenated text APT via an optical disk drive to an optical disk.

The output unit has a function of outputting encrypted concatenated data that has been encrypted by the encrypting unit on the basis of the predetermined block length bl. The encrypted concatenated data corresponds to one encrypted block or a series of encrypted blocks generated by encrypting the concatenated text APT on the basis of the block length bl.

For example the output unit causes the I F to transmit the encrypted blocks generated by encrypting the concatenated text APT on the basis of the block length bl via the network to the tampering detection apparatus . If an initial vector IV is used at the time of encryption by the encrypting unit the initial vector IV is transmitted along with the encrypted blocks. The initial vector IV need not be confidential information and may be transmitted without encryption. The output unit outputs the encrypted blocks generated by encrypting the concatenated text APT on the basis of the block length bl via an optical disk drive to an optical disk.

The encrypting unit has a function of encrypting on the basis of the predetermined block length bl the concatenated data by using a key used for encryption and decryption in common. The key used for encryption and decryption in common is a common key. For example the encrypting unit divides the concatenated text APT by the block length bl followed by encryption by block cipher using the common key to generate the encrypted blocks.

For example the encrypting unit uses the encryption circuit of the Data Encryption Standard DES method or the Advanced Encryption Standard AES method for the encryption. The DES method uses the block length bl 8 bytes and the AES method uses the block length bl 16 bytes . Multiple operation modes are prescribed in each of the encryption methods and specific encryption and decryption processes are executed depending on these operation modes.

The operation modes usable in both the DES method and the AES method include the Electronic Codebook ECB mode the Cipher Block Chaining CBC mode the Cipher Feedback CFB mode the Output Feedback OFB mode and the Counter CTR mode. For the initial vector IV used for the encryption for example random numbers generated for each encryption can be employed.

As a result the encrypting unit can encrypt on the basis of the block length bl the concatenated text APT by block cipher using the common key to ensure confidentiality of the concatenated text APT.

The third generating unit has a function of generating a third code that identifies the first code and is of a remaining data length acquired by subtracting the data length of the first code and a predetermined data length from the data length difference. The third code is a code corresponding to the padding length pl.

For example the third generating unit generates a code having a data length of a remaining area that is extracted from the beginning of a code acquired by sequentially arranging one byte codes indicating the padding length. As a result the third generating unit can generate the code used as an index for determining whether the padding length pl is correct at the tampering detection apparatus .

A functional configuration example of the tampering detection apparatus will be described with reference to .

The input unit has a function of inputting encrypted data acquired by encrypting the plain text data on the basis of the predetermined block length bl. The plain text data corresponds to the plain text PT described above. The encrypted data corresponds to the encrypted blocks described above.

For example the input unit receives the encrypted blocks from the information processing apparatus through the I F via the network . The input unit reads the encrypted blocks from an optical disk via an optical disk drive. As a result the input unit can input the encrypted blocks that are to be checked for tampering.

The decrypting unit has a function of generating from the encrypted data input by the input unit decrypted data that is decrypted by using a key that is used for encryption and decryption in common. The key used for encryption and decryption in common is the common key. If decrypted from non tampered encrypted blocks the decrypted data is the concatenated text APT of the information processing apparatus . However if decrypted from tampered encrypted blocks the decrypted data is a concatenated text APT having contents that differs from the concatenated text APT of the information processing apparatus .

For example the decrypting unit uses the CBC mode of the block cipher using the common key to decrypt the concatenated text APT or the concatenated text APT from an initial Vector IV and the encrypted blocks. The initial vector IV is the same data as the initial Vector IV used in the encryption by the information processing apparatus . As a result the decrypting unit can decrypt the concatenated text from the encrypted blocks.

The first extracting unit has a function of extracting the first code from a first area at the end of the encrypted data storing the data length of the padding pd. The first area is the padding length area described above. If the encrypted blocks have not been subject to tampering or if the padding pd has not been affected by tampering the first code is the padding length pl. On the other hand if the padding pd has been affected by tampering the first code is a meaningless code.

For example the first extracting unit refers to the last 4 bits of the concatenated text decrypted by the decrypting unit to extract bytes presumed to be the padding length pl. As a result the first extracting unit can extract the data length presumed to be the padding length pl.

The determining unit has a function of determining based on the data length indicated by the first code extracted by the first extracting unit a second area of the decrypted data storing a code calculated from the plain text data. The second area is a storage area of the code calculated from the plain text PT estimated from the padding length pl extracted by the first extracting unit .

For example the determining unit determines as the second area an area adjacent to the beginning of the first area and having a remaining data length acquired by subtracting the data length of the first area from the data length indicated by the first code. For example if the padding length pl is 4 bytes the first extracting unit determines an area of 28 bits adjacent to the beginning of the padding length area. As a result the determining unit can determine the area presumed to be the storage area storing the code calculated from the plain text PT by the information processing apparatus .

For example the determining unit determines as a fourth area an area in the decrypted data adjacent to the beginning of the second area and having a remaining data length acquired by subtracting the data length of the first code and a predetermined data length from the data length indicated by the first code. As a result the determining unit can determine the area presumed to be the area having the code corresponding to the padding stored by the information processing apparatus .

The second extracting unit has a function of extracting the second code from the second area determined by the determining unit . If the encrypted blocks have not been subject to tampering or if the padding pd has not been affected by tampering the second code is a code e.g. CRC calculated from the plain text PT and stored by the information processing apparatus . On the other hand if the padding pd has been affected by tampering the second code is a meaningless code affected by tampering.

For example the second extracting unit extracts from the area presumed to be the storage area of the CRC the CRC stored by the information processing apparatus or a meaningless code affected by tampering. As a result the second extracting unit can extract the code used as an index for detection of tampering.

The third extracting unit has a function of extracting the third code from a third area of the decrypted data exclusive of an ending area of the decrypted data of the data length indicated by the first code. The ending area is an area at the end of the concatenated text decrypted by the decrypting unit and if the encrypted blocks have not been subject to tampering or if the padding pd has not been affected by tampering the ending area is the padding pd. On the other hand the ending area is an area at the end of the concatenated text decrypted by the decrypting unit and if the padding pd has been affected by tampering the ending area is a meaningless area.

For example the third extracting unit extracts the plain text PT of the information processing apparatus or tampered plain text PT exclusive of the tail data presumed to be the padding pd. As a result the third extracting unit can extract the plain text that is to be checked for tampering.

The generating unit has a function of generating a fourth code that identifies the third code extracted by the third extracting unit and is of the same data length as the data length of the second code. The fourth code is a code identifying the third code and is for example a hash value e.g. CRC calculated by a hash function from the third code or a parity code acquired from the third code.

For example if the second code is 28 bits a 28 bit CRC is generated from the third code. As a result the generating unit can generate a code calculated from the plain text PT of the information processing apparatus or a code calculated from the tampered plain text PT . The length of the second code may be shared in advance as is the case with the key.

The judging unit has a function of judging whether the fourth code generated by the generating unit and the second code coincide. For example the judging unit judges whether the CRC calculated from the plain text PT and the CRC stored in the padding pd coincide.

The judging unit judges whether the CRC calculated from the plain text PT affected by the tampering of the encrypted blocks and the CRC stored in the padding pd coincide. The judging unit judges whether the CRC calculated from the plain text PT affected by the tampering of the encrypted blocks and a CRC stored in the padding pd affected by the tampering of the encrypted blocks coincide.

As a result if the plain text extracted by the third extracting unit has not been affected by tampering coincidence is determined from the coincidence judgment and the judging unit can judge that no tampering has occurred. If the plain text extracted by the third extracting unit has been affected by tampering non coincidence is judged from the coincidence judgment and the judging unit can judge that tampering has occurred.

The judging unit has a function of judging whether a code identified by a fifth code extracted by a fourth extracting unit and the first code coincide. For example the judging unit judges whether the code extracted by the first extracting unit from the code corresponding to the padding length pl stored by the information processing apparatus is the correct code. As a result if the code is not the correct code the judging unit can judge that tampering has occurred.

The output unit has a function of outputting a judgment result obtained by the judging unit . For example the output unit outputs to the display indication that the fourth code coincides with the second code i.e. that the received encrypted blocks have not been subject to tampering. Alternatively the output unit outputs to the display indication that that the fourth code does not coincide with the second code i.e. that the received encrypted blocks have been subject to tampering.

As a result the output unit can output indication whether the received encrypted blocks have been subject to tampering i.e. whether the plain text extracted by the third extracting unit has been affected by tampering. The output unit outputs the decrypted data of the decryption result to the disk.

The fourth extracting unit has a function of extracting the fifth code from the fourth area storing the code that identifies the first code. For example the fourth extracting unit extracts a code stored in the area that is determined by the determining unit and is presumed to have the code corresponding to the padding length pl stored by the information processing apparatus . As a result if the padding pd has not been affected by tampering the fourth extracting unit can extract the code corresponding to the padding length pl stored by the information processing apparatus .

The CRC storage area is an area adjacent to the beginning of the padding length area. The padding length area length ll has a data length of 4 bits i.e. a minimum data length necessary for indicating the block length bl 16 bytes . The CRC storage area length cl is up to 32 bits . The contents of the padding pd are in hexadecimal. However the CRC is denoted by .

If the padding pd has a remaining area other than the padding length area and the storage area a code corresponding to the padding length pl is stored in the remaining area. The code corresponding to the padding length pl is a code having the data length of the remaining area extracted from the beginning of a code acquired by sequentially arranging one byte codes indicating the padding length.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 1 byte of the padding pd is necessary for encrypting the plain text PT by block cipher. The padding pd includes 1 indicating the padding length pl of 1 byte in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is the remaining 4 bits adjacent to the beginning of the padding length area.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 2 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 2 indicating the padding length pl of 2 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is the remaining 12 bits adjacent to the beginning of the padding length area.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 3 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 3 indicating the padding length pl of 3 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is the remaining 20 bits adjacent to the beginning of the padding length area.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 4 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 4 indicating the padding length pl of 4 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is the remaining 28 bits adjacent to the beginning of the padding length area.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 5 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 5 indicating the padding length pl of 5 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is 32 bits of the remaining 36 bits adjacent to the beginning of the padding length area.

The padding pd includes a code 0 corresponding to the padding length pl 5 bytes in the remaining 4 bits . The code 0 is the first 4 bits of 05050505 . . . acquired by sequentially arranging one byte codes indicating the padding length.

The plain text PT is data having a data length bytes longer than a multiple of the block length bl. Therefore 6 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 6 indicating the padding length pl of 6 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is 32 bits of the remaining 44 bits adjacent to the beginning of the padding length area.

The padding pd includes a code 060 corresponding to the padding length pl 6 bytes in the remaining 12 bits . The code 060 is the first 12 bits of 06060606 . . . acquired by sequentially arranging one byte codes indicating the padding length.

The plain text PT is data of a length that is a multiple of the block length bl. However if the padding pd is not concatenated information indicating the absence of concatenation of the padding pd must be concatenated to the plain text PT resulting in the plain text PT having a data length that is not a multiple of the block length bl. Thus even if the plain text PT is data having a length that is a multiple of the block length bl the padding pd must be concatenated.

Therefore 16 bytes of the padding pd are necessary for encrypting the plain text PT by block cipher. The padding pd includes 0 indicating the padding length pl of 16 bytes in the padding length area that is the last 4 bits and includes the CRC acquired from the plain text PT in the storage area that is 32 bits of the remaining 124 bits adjacent to the beginning of the padding length area.

Further the padding pd includes in the remaining 92 bits a code 10101010101010101010101 corresponding to the padding length pl 16 byte . The code 10101010101010101010101 is the first 92 bits of 101010101010101010101010 . . . acquired by sequentially arranging one byte codes indicating the padding length pl.

The storage area may be implemented by employing the first 32 bits of the padding pd at maximum. The storage area may be implemented by employing the entire remaining area of the padding pd without setting the threshold value of 32 bits .

A hash value may be employed as the code calculated from the plain text PT and stored in the storage area. Alternatively parity may be employed as the code calculated from the plain text PT and stored in the storage area. A hash value or parity may be employed as the code corresponding to the padding length pl.

If a CRC of each data length is calculated the CRC may be calculated from a CRC calculation function corresponding to each data length. The CRC may be calculated by calculating a CRC for a predetermined data length regardless of the padding length pl and extracting a code having a necessary data length from the beginning. For example if the padding length pl is 8 bits the information processing apparatus calculates a 32 bit CRC and extracts and stores the first 4 bits of the CRC into the storage area.

A first specific example of tampering detection will be described with reference to . In this example the information processing apparatus uses the CBC mode of the block cipher for encryption. The tampering detection apparatus uses the CBC mode of the block cipher for decryption.

Therefore the information processing apparatus concatenates to the plain text PT 7 bytes of the padding pd to thereby generate the concatenated text APT for the encryption by block cipher. The information processing apparatus divides the concatenated text APT by the block length bl to generate blocks B to Bnk. The information processing apparatus encrypts the blocks B to Bn with the CBC mode of the block cipher to generate encrypted blocks C to Cn.

For example the information processing apparatus concatenates to the plain text PT the padding pd ending with 7 indicating the padding length pl 7 bytes including a 32 bit CRC 63350373 and having 07070 corresponding to the padding length pl 7 bytes as the remainder.

The information processing apparatus divides the concatenated text APT concatenated with the padding pd by the block length bl to generate the blocks B to Bn. The generated block Bn includes the padding pd.

The information processing apparatus encrypts each of the generated blocks B to Bn to generate the encrypted blocks C to Cn. For example if encrypting the first block B from the beginning the information processing apparatus calculates exclusive OR between the block B and the initial vector IV and performs encryption with the common key to generate the encrypted block C. If encrypting the i th block Bi from the beginning the information processing apparatus calculates exclusive OR between the block Bi and the encrypted block Ci and performs encryption with the common key to generate the encrypted block Ci.

The information processing apparatus transmits the generated encrypted blocks C to Cn to the tampering detection apparatus . The tampering detection by the tampering detection apparatus upon receiving the transmitted encrypted blocks C to Cn will be described.

For example the tampering detection apparatus decrypts the blocks B to Bn from the encrypted blocks C to Cn. For example if decrypting the first encrypted block C from the beginning the tampering detection apparatus decrypts the encrypted block C with the common key and calculates exclusive OR with the initial vector IV to generate the block B. If decrypting the i th encrypted block Ci from the beginning the tampering detection apparatus decrypts the encrypted block Ci with the common key and calculates exclusive OR with the encrypted block Ci to generate the block Bi.

The tampering detection apparatus extracts the padding length pl from the padding length area at the end of the generated final block Bn. The tampering detection apparatus extracts at the end of the padding pd and determines that the padding length pl is 7 bytes .

The tampering detection apparatus extracts the code corresponding to the padding length pl from the padding pd so as to determine whether the extracted padding length pl 7 bytes is correct. The code corresponding to the padding length is extracted as 07070 . The code corresponding to the padding length is 07070 which is the same as the extracted code and therefore the tampering detection apparatus determines that the padding length pl 7 bytes is correct.

The tampering detection apparatus extracts the CRC from the padding pd. Since the padding length pl is 7 bytes the tampering detection apparatus determines that the CRC storage area length is 32 bits . The tampering detection apparatus extracts the CRC 63350373 from the CRC storage area.

The tampering detection apparatus determines and removes the last 7 bytes of data of the decrypted block Bn as the padding pd to thereby generate the plain text PT. The tampering detection apparatus generates the 32 bit CRC from the plain text PT after the padding pd is removed.

The tampering detection apparatus judges whether the extracted CRC and the generated CRC coincide to detect the presence or absence of tampering. If the plain text PT generated by the tampering detection apparatus is the same as the plain text PT of the information processing apparatus the CRCs generated from the respective plain texts PT are the same.

Since the encrypted blocks C to Cn have not been subject to tampering in this case the CRC generated by the tampering detection apparatus is the same as the CRC stored into the padding pd by the information processing apparatus . Therefore the tampering detection apparatus determines that the received encrypted blocks C to Cn have not been subject to tampering and that the plain text PT acquired by removing the padding pd in the tampering detection apparatus has not changed from the plain text PT of the information processing apparatus .

A second specific example of tampering detection will be described with reference to . In this example the information processing apparatus uses the CBC mode of the block cipher for encryption. The tampering detection apparatus uses the CBC mode of the block cipher for decryption.

However it is assumed that the transmitted encrypted blocks C to Cn are captured by an attacker on during transmission. The attacker tampers and changes the encrypted block Cn to the encrypted block Cn .

Among the blocks decrypted by the tampering detection apparatus blocks decrypted based on the tampered encrypted block Cn are different from the blocks B to Bn of the information processing apparatus . In other words blocks Bn and Bn that are different from the blocks Bn and Bn are generated from the encrypted block Cn and Cn from which the blocks Bn and Bn should be generated by the decryption at the tampering detection apparatus . This causes a change in the contents of the padding pd.

The tampering detection apparatus extracts the padding length pl from the padding length area at the end of the generated final block Bn . The tampering detection apparatus extracts at the end and determines that the padding length pl is 6 bytes .

The tampering detection apparatus extracts the code corresponding to the padding length pl from the padding pd so as to determine whether the extracted padding length pl 6 bytes is correct. Since the padding pd is changed 651 is extracted as the code corresponding to the padding length pl. Since the code corresponding to the padding length pl is 060 and different from the extracted code the tampering detection apparatus determines that the padding length pl 6 bytes is wrong.

As a result the tampering detection apparatus determines that the padding pd has been changed by tampering of the encrypted blocks. The tampering detection apparatus determines that the contents of the plain text PT acquired by removing the padding pd by the tampering detection apparatus have been changed consequent to tampering of the encrypted blocks without performing the coincidence judgment of the CRC.

The tampering is also detected with the coincidence judgment of the CRC. The tampering detection apparatus extracts the CRC from the padding pd. Since the padding length pl is 6 bytes the tampering detection apparatus determines that the CRC storage area length is 32 bits . The tampering detection apparatus extracts a CRC 651988243A from the CRC storage area.

The tampering detection apparatus determines and removes the last 6 bytes of data of the decrypted block Bn as the padding pd to thereby generate plain text. Since the blocks Bn and Bn have been affected by tampering a plain text PT that is different from the plain text PT of the information processing apparatus is generated. The tampering detection apparatus generates a 32 bit CRC from the plain text PT after the padding pd is removed.

The tampering detection apparatus judges whether the extracted CRC and the generated CRC coincide to detect the presence or absence of tampering. If the plain text PT generated by the tampering detection apparatus is the same as the plain text PT of the information processing apparatus the CRCs generated from the respective plain texts are the same.

In this case consequent to the tampering of the encrypted block Cn the stored CRC is changed to the CRC . The CRC is generated from the plain text PT that has changed consequent to the effect of the tampering of the encrypted block Cn . Therefore the CRC stored in the padding pd is different from the CRC generated by the tampering detection apparatus . Thus the tampering detection apparatus can determine that the contents of the plain text PT acquired by removing the padding pd in the tampering detection apparatus are changed due to the effect of the tampering of the encrypted blocks.

A third specific example of tampering detection will be described with reference to . In this example the information processing apparatus uses the CBC mode of the block cipher for encryption. The tampering detection apparatus uses the CBC mode of the block cipher for decryption.

However it is assumed that the transmitted encrypted blocks C to Cn are captured by an attacker during transmission. The attacker tampers and changes the encrypted block C to the encrypted block C .

Among the blocks decrypted by the tampering detection apparatus blocks decrypted based on the tampered encrypted block C are different from the blocks B to Bn of the information processing apparatus . In other words blocks B and B which are different from the blocks B and B are generated from the encrypted block C and C from which the blocks B and B should be generated by the decryption at the tampering detection apparatus . This causes no change in the contents of the padding pd.

The tampering detection apparatus extracts the padding length pl from the padding length area at the end of the generated final block Bn. The tampering detection apparatus extracts at the end and determines that the padding length pl is 7 bytes .

The tampering detection apparatus extracts the code corresponding to the padding length pl from the padding pd so as to determine whether the extracted padding length pl 7 bytes is correct. Since the padding pd has not changed the code corresponding to the padding length is extracted as 07070 . The code corresponding to the padding length is 07070 which is the same as the extracted code and therefore the tampering detection apparatus determines that the padding length pl 7 bytes is correct.

The tampering detection apparatus extracts the CRC from the padding pd. Since the padding length pl is 7 bytes the tampering detection apparatus determines that the CRC storage area length is 32 bits . The tampering detection apparatus extracts the CRC 63350373 from the CRC storage area.

The tampering detection apparatus determines and removes the last 7 bytes of data of the decrypted block Bn as the padding pd to thereby generate plain text. Since the blocks B and B are affected by tampering a plain text PT different from the plain text PT of the information processing apparatus is generated. The tampering detection apparatus generates a 32 bit CRC from the plain text PT after the padding pd is removed.

The tampering detection apparatus determines whether the extracted CRC and the generated CRC coincide to detect the presence or absence of tampering. If the plain text PT generated by the tampering detection apparatus is the same as the plain text PT of the information processing apparatus the CRCs generated from the respective plain texts are the same.

In this case the CRC is generated from the plain text PT that has changed consequent to the tampering of the encrypted block C . Therefore the CRC stored in the padding pd is different from the CRC generated by the tampering detection apparatus . Thus the tampering detection apparatus can determine that the contents of the plain text PT acquired by removing the padding pd in the tampering detection apparatus have changed consequent to tampering of the encrypted blocks.

Details of the padding concatenating process executed by the information processing apparatus will be described with reference to .

The CPU calculates the padding length pl of the padding pd to be concatenated to the input plain text PT step S . The CPU concatenates to the end of the plain text PT the padding pd having the calculated padding length pl step S .

The CPU calculates the CRC corresponding to the calculated padding length pl step S . The CPU stores the calculated CRC into the CRC storage area of the padding pd step S .

The CPU encrypts the concatenated text APT storing the CRC with the CBC mode of the block cipher on the basis of the block length bl step S . The CPU outputs the encrypted blocks after the encryption step S and terminates the padding concatenating process.

As a result the information processing apparatus can create the padding pd that includes the code which indicates the padding length pl at the end and that includes the code calculated from the plain text PT in the storage area. As a result if the padding pd has a remaining area other than the padding length area and the storage area the information processing apparatus can create the padding pd to include in the remaining area the code corresponding to the padding length pl. The information processing apparatus can concatenate the created padding pd to the input plain text PT to create the concatenated text APT.

Details of the tampering detection process executed by the tampering detection apparatus will be described with reference to .

The CPU decrypts the plain text from the encrypted blocks with the CBC mode of the block cipher step S . The CPU extracts the padding length pl from the end and calculates the CRC storage area length based on the padding length pl step S . The CPU extracts the CRC from the storage area step S .

The CPU determines if the padding length pl is equal to or less than 4 bytes step S . If the padding length pl is equal to or less than 4 bytes step S YES the process goes to step S.

On the other hand if the padding length pl is not equal to or less than 4 bytes step S NO the CPU determines whether the padding length pl is correct step S . If the padding length pl is correct step S YES the process goes to step S.

On the other hand if the padding length pl is wrong step S NO the CPU determines that tampering has occurred and outputs the determination result step S and terminates the tampering detection process.

At step S the CPU removes the padding pd from the decrypted plain text step S . The CPU calculates the CRC from the plain text after removing the padding step S .

The CPU judges whether the CRC extracted at step S is coincides with the CRC calculated at step S step S . If coincident step S YES the CPU judges that no tampering has occurred outputs the decrypted plain text step S and terminates the tampering detection process.

On the other hand if not coincident step S NO the CPU judges that tampering has occurred outputs the determination result step S and terminates the tampering detection process.

As a result if the padding pd includes the code corresponding to the padding length pl the tampering detection apparatus can determine whether the padding length pl is correct thereby determining whether the effect of tampering of the encrypted blocks extends to the padding pd.

The tampering detection apparatus judges whether the code calculated from the plain text PT of the information processing apparatus included in the padding pd and the code calculated from the plain text acquired by the tampering detection apparatus coincide. Therefore the tampering detection apparatus can determine whether the plain text acquired by the tampering detection apparatus has changed from the plain text PT of the information processing apparatus consequent to tampering of the encrypted blocks.

As described above the information processing apparatus calculates the padding length pl of the padding concatenated to the plain text PT and then calculates the storage area length cl of the code calculated from the plain text PT within a range of the padding length pl. This enables the code calculated from the plain text PT to be generated of a data length that can be stored in the padding pd. As a result since the storage of the generated code calculated from the plain text PT into the padding pd does not increase the data length of the padding pd the data length of the concatenated text APT can be prevented from increasing and a amount of used resources can be reduced.

The tampering detection apparatus judges whether the code calculated from the plain text acquired by decryption and the code calculated from the plain text PT stored in the padding pd coincide. As a result it can be detected that the plain text has changed consequent to tampering of the encrypted blocks.

The information processing apparatus ensures the padding length area at the end of the padding pd when calculating the storage area. As a result based on the data length indicated by the code of the padding length area at the end the tampering detection apparatus can remove the padding pd from the concatenated text APT for which tampering is not detected thereby acquiring the plain text PT that is the same as the plain text PT of the information processing apparatus .

The information processing apparatus generates the padding length area length ll to be the shortest data length capable of indicating the block length bl. As a result the code indicating the padding length pl can be stored in a minimum necessary data length.

The information processing apparatus generates the padding pd to a minimum data length necessary for encrypting the plain text PT. As a result an increase in the amount of transmission data due to concatenation of the padding pd can be minimized.

The information processing method and the tampering detection method described in the present embodiment may be implemented by executing a prepared program on a computer such as a personal computer and a workstation. The program is stored on a computer readable recording medium such as a hard disk a flexible disk a CD ROM an MO and a DVD read out from the computer readable medium and executed by the computer. The program may be distributed through a network such as the Internet.

An aspect of the present embodiment produces an effect that detection of tampering of overall plain text can be achieved without increasing used resources.

All examples and conditional language provided herein are intended for pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed as limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although one or more embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

