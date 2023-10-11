SRC1:= \
../src/crl.c \
../src/dtls.c \
../src/dtls13.c \
../src/internal.c \
../src/internal2.c \
../src/keys.c \
../src/ocsp.c \
../src/ssl.c \
../src/tls.c \
../src/tls13.c \
../src/wolfio.c \

SRC2:= \
../wolfcrypt/src/aes.c \
../wolfcrypt/src/arc4.c \
../wolfcrypt/src/asn.c \
../wolfcrypt/src/blake2b.c \
../wolfcrypt/src/blake2s.c \
../wolfcrypt/src/camellia.c \
../wolfcrypt/src/chacha.c \
../wolfcrypt/src/chacha20_poly1305.c \
../wolfcrypt/src/cmac.c \
../wolfcrypt/src/coding.c \
../wolfcrypt/src/cpuid.c \
../wolfcrypt/src/curve25519.c \
../wolfcrypt/src/curve448.c \
../wolfcrypt/src/des3.c \
../wolfcrypt/src/dh.c \
../wolfcrypt/src/dsa.c \
../wolfcrypt/src/ecc.c \
../wolfcrypt/src/ed25519.c \
../wolfcrypt/src/ed448.c \
../wolfcrypt/src/error.c \
../wolfcrypt/src/fe_low_mem.c \
../wolfcrypt/src/fe_operations.c \
../wolfcrypt/src/ge_low_mem.c \
../wolfcrypt/src/ge_operations.c \
../wolfcrypt/src/hash.c \
../wolfcrypt/src/hmac.c \
../wolfcrypt/src/integer.c \
../wolfcrypt/src/kdf.c \
../wolfcrypt/src/logging.c \
../wolfcrypt/src/md2.c \
../wolfcrypt/src/md4.c \
../wolfcrypt/src/md5.c \
../wolfcrypt/src/memory.c \
../wolfcrypt/src/pkcs12.c \
../wolfcrypt/src/pkcs7.c \
../wolfcrypt/src/poly1305.c \
../wolfcrypt/src/pwdbased.c \
../wolfcrypt/src/random.c \
../wolfcrypt/src/rc2.c \
../wolfcrypt/src/ripemd.c \
../wolfcrypt/src/rsa.c \
../wolfcrypt/src/sha.c \
../wolfcrypt/src/sha256.c \
../wolfcrypt/src/sha3.c \
../wolfcrypt/src/sha512.c \
../wolfcrypt/src/signature.c \
../wolfcrypt/src/sp_c32.c \
../wolfcrypt/src/sp_c64.c \
../wolfcrypt/src/sp_int.c \
../wolfcrypt/src/sp_x86_64.c \
../wolfcrypt/src/srp.c \
../wolfcrypt/src/tfm.c \
../wolfcrypt/src/wc_encrypt.c \
../wolfcrypt/src/wc_pkcs11.c \
../wolfcrypt/src/wc_port.c \
../wolfcrypt/src/win16_port.c \
../wolfcrypt/src/wolfevent.c \
../wolfcrypt/src/wolfmath.c \

OBJ1:=$(SRC1:../src/%.c=%.o)
OBJ2:=$(SRC2:../wolfcrypt/src/%.c=%.o)
OBJ:=$(OBJ1) $(OBJ2)

DLL:=wolfssl.dll
CC=wcl -lwindows_dll -bt=windows
CFLAGS=-za99
CFLAGS+=-ml
CFLAGS+=-i../
CFLAGS+=-dHAVE_CONFIG_H -dWOLFSSL_USER_SETTINGS -dBUILDING_WOLFSSL -dWIN16 -dWOLFSSL_DLL

all: $(DLL)

clean:
	rm -f $(DLL) $(OBJ)

$(DLL): $(OBJ)
	$(CC) -fe=$@ $^

$(OBJ1): %.o: ../src/%.c
	$(CC) -c $(CFLAGS) $<

$(OBJ2): %.o: ../wolfcrypt/src/%.c
	$(CC) -c $(CFLAGS) $<
