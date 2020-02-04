---
title: 'Lync Server 2013: solução de problemas com o plug-in VDI do Lync'
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Solução de problemas do plug-in VDI do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Solucionando problemas com a instalação do plug-in VDI do Lync em um cliente Thin

Se houver problemas para instalar o plug-in VDI em um cliente leve, verifique o seguinte:

  - Verifique se há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.

  - Verifique se a proteção contra gravação está desativada. Consulte a documentação do fabricante do seu dispositivo para obter instruções.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Solução de problemas de emparelhamento

Quando o emparelhamento de plug-in do VDI falha, o ícone de emparelhamento no canto inferior direito é exibido como um "X" vermelho, conforme mostrado:

![Ícone de VDI do Lync mostrando o emparelhamento com êxito](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone de VDI do Lync mostrando o emparelhamento com êxito")

Estes são os possíveis motivos para falhas e as ações corretivas que você pode executar.

  - **O usuário inseriu credenciais incorretas durante a entrada.**
    
    O usuário deve desconectar-se do Lync e entrar novamente com as credenciais corretas. A caixa de diálogo de emparelhamento será exibida novamente e mostrará se o emparelhamento foi bem-sucedido.

  - **Outra instância do cliente de área de trabalho remota está sendo executada.**
    
    Se eles estiverem usando a conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:
    
    1.  Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete** e depois clicar em **Iniciar Gerenciador de Tarefas**.
    
    2.  Clicar na guia **Processos** e procurar todos os processos chamados **mstsc.exe** na lista.
    
    3.  Realçar cada processo **mstsc.exe** e clicar em **Finalizar Processo**. 
    
    4.  Iniciar uma nova sessão de área de trabalho remota e tentar conectar-se novamente. 

  - **Os arquivos necessários não foram instalados corretamente.**
    
    Após a instalação do plug-in no computador local, os seguintes arquivos devem estar presentes em C:\\arquivos\\de programas Microsoft Office\\Office15 (ou na letra de unidade apropriada):
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Se houver algum problema com o emparelhamento com VDI, verifique se esses arquivos estão presentes no computador local.

  - **O cliente do Lync está em execução no computador local.**
    
    Para usar o plug-in VDI do Lync, um cliente do Lync não deve estar em execução no computador local, caso contrário, haverá falha na junção. Como prática recomendada, o usuário não deve instalar um cliente do Lync no computador local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

