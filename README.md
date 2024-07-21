__Eduarda dos Santos da Silva__

O desafio é não poder criar variáveis e sim um buffer de memória (void *pBuffer). Nisso foi feito o trabalho que o Sistema Operacional faria para organizar a memória.

As regras são:
1. __Nenhuma variável pode ser declarada em todo o programa__, somente ponteiros. Todos os dados do programa devem ser guardados dentro do pBuffer.
Nem mesmo como parâmetro de função. Só ponteiros que apontam para dentro do pBuffer.
__Exemplo do que não pode:__ int c; char a; int v[10];  void Funcao(int parametro)
__Não pode usar struct em todo o programa.__
2. Usar fila ordenada (heap) para armazenar as pessoas em ordem alfabética sempre que o usuário incluir uma nova pessoa.
Implementar a base de dados da agenda usando lista duplamente ligada
Somente essa base de dados pode ficar fora do buffer principal, ou seja, pode usar um malloc para cada nodo.

No final é gravado um vídeo explicando a lógica utilizada por trás desse código, além de mostrar os resultados dos testes e em conjunto o resultado após passar no DrMemory ou Valgrind.

Abaixo, irei deixar esses resultados que me foram dados pelo DrMemory:

"Dr. Memory version 2.6.0 build 0 built on Sep 21 2023 17:48:48
Windows version: WinVer=105;Rel=2009;Build=19045;Edition=Enterprise
Dr. Memory results for pid 6300: "pBuffer.exe"
Application cmdline: ""D:\UsuÃ¡rios\Eduarda\Ãrea de Trabalho\agenda-pbuffer\output\pBuffer.exe""
Recorded 124 suppression(s) from default D:\UsuÃ¡rios\Eduarda\Ãrea de Trabalho\bin\suppress-default.txt

Error #1: UNINITIALIZED READ: reading register eax
# 0 KERNELBASE.dll!FindNextFileW      +0x20e    (0x762aedde <KERNELBASE.dll+0x10edde>)
# 1 KERNELBASE.dll!FindNextFileA      +0x33     (0x762ad264 <KERNELBASE.dll+0x10d264>)
# 2 .text                              [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 3 __mingw_glob                       [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 4 _setargv                           [d:/Usuários/Eduarda/Área de Trabalho/agenda-pbuffer/pBuffer.c:250]
# 5 .text      
# 6 mainCRTStartup
# 7 ntdll.dll!__RtlUserThreadStart
Note: @0:00:00.265 in thread 4292
Note: instruction: cmp    %eax $0x0000001a

Error #2: UNINITIALIZED READ: reading register eax
# 0 KERNELBASE.dll!FindNextFileW      +0x23b    (0x762aee0b <KERNELBASE.dll+0x10ee0b>)
# 1 KERNELBASE.dll!FindNextFileA      +0x33     (0x762ad264 <KERNELBASE.dll+0x10d264>)
# 2 .text                              [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 3 __mingw_glob                       [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 4 _setargv                           [d:/Usuários/Eduarda/Área de Trabalho/agenda-pbuffer/pBuffer.c:250]
# 5 .text      
# 6 mainCRTStartup
# 7 ntdll.dll!__RtlUserThreadStart
Note: @0:00:00.265 in thread 4292
Note: instruction: data16 mov    %cx -> 0x00000234(%ebx,%eax,2)

Error #3: UNINITIALIZED READ: reading register eax
# 0 KERNELBASE.dll!FindNextFileW      +0x167    (0x762aed37 <KERNELBASE.dll+0x10ed37>)
# 1 KERNELBASE.dll!FindNextFileA      +0x33     (0x762ad264 <KERNELBASE.dll+0x10d264>)
# 2 .text                              [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 3 __mingw_glob                       [../../../src/gcc-6.3.0/libgcc/config/i386/cygwin.S:184]
# 4 _setargv                           [d:/Usuários/Eduarda/Área de Trabalho/agenda-pbuffer/pBuffer.c:250]
# 5 .text      
# 6 mainCRTStartup
# 7 ntdll.dll!__RtlUserThreadStart
Note: @0:00:00.265 in thread 4292
Note: instruction: test   %eax %eax

===========================================================================
FINAL SUMMARY:

DUPLICATE ERROR COUNTS:
	Error #   1:      2
	Error #   2:      2

SUPPRESSIONS USED:

ERRORS FOUND:
      0 unique,     0 total unaddressable access(es)
      3 unique,     5 total uninitialized access(es)
      0 unique,     0 total invalid heap argument(s)
      0 unique,     0 total GDI usage error(s)
      0 unique,     0 total handle leak(s)
      0 unique,     0 total warning(s)
      0 unique,     0 total,      0 byte(s) of leak(s)
      0 unique,     0 total,      0 byte(s) of possible leak(s)
ERRORS IGNORED:
      6 unique,     6 total,   4457 byte(s) of still-reachable allocation(s)
         (re-run with "-show_reachable" for details)
Details: D:\UsuÃ¡rios\Eduarda\Ãrea de Trabalho\drmemory\logs\DrMemory-pBuffer.exe.6300.000\results.txt"

Os erros mostrados são os que o DrMemory encontra até mesmo na bibliotecas utilizadas, visto isso eles devem ser ignorados por não serem relevantes e não se tratar do código.

