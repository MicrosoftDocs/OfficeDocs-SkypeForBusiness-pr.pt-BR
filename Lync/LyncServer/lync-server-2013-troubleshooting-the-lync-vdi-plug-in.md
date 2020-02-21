---
title: 'Lync Server 2013: solução de problemas do plug-in do Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc58629ea7c641427347600be48538cd555022c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Solucionando problemas do plug-in do Lync VDI no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Solucionando problemas com a instalação do plug-in do Lync VDI em um cliente fino

Caso existam problemas com a instalação de um plug-in VDI em um cliente fino, verifique o seguinte:

  - Assegure-se de que há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.

  - Assegure-se de que a proteção contra gravação está desligada. Consulte a documentação do fabricante do seu dispositivo para instruções.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Solucionando problemas com pareamento

Quando o pareamento do plug-in VDI falha, o ícone de pareamento no canto inferior direito é exibido como um "X" vermelho, como mostrado a seguir:

![Ícone do Lync VDI mostrando emparelhamento bem-sucedido](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone do Lync VDI mostrando emparelhamento bem-sucedido")

A seguir estão possíveis razões para falhas e as ações corretivas que você pode tomar.

  - **O usuário inseriu credenciais incorretas durante a entrada.**
    
    O usuário deve sair do Lync e entrar novamente com as credenciais corretas. A caixa de diálogo de pareamento reaparecerá e mostrará se o pareamento teve êxito.

  - **Outra instância do cliente de área de trabalho remota está sendo executada.**
    
    Se eles estiverem usando a conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:
    
    1.  Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete**, e então clicar em **Iniciar Gerenciador de Tarefas**.
    
    2.  Clique na guia **Processos** e procure por todos os processos chamados **mstsc.exe** na lista.
    
    3.  Selecione cada processo **mstsc.exe** e então clique em **Finalizar Processo**.
    
    4.  Inicie uma nova sessão de área de trabalho remota e tente conectar novamente.

  - **Os arquivos necessários não foram instalados corretamente.**
    
    Depois que o plug-in é instalado no computador local, os seguintes arquivos devem estar presentes em C:\\arquivos\\de programa Microsoft\\Office Office15 (ou a letra de unidade apropriada):
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    Caso existam quaisquer problemas com o pareamento VDI, verifique para se assegurar que estes arquivos estão presentes no computador local.

  - **O cliente Lync está em execução no computador local.**
    
    Para usar o plug-in do Lync VDI, um cliente do Lync não deve estar em execução no computador local, caso contrário, o emparelhamento falhará. Como prática recomendada, o usuário não deve instalar um cliente Lync no computador local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

