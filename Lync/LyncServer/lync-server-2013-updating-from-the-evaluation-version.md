---
title: 'Lync Server 2013: atualizando a versão de avaliação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Atualização da versão de avaliação do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-20_

Se você instalou a versão de avaliação do Microsoft Lync Server 2013, eventualmente precisará atualizar essa instalação uma cópia licenciada do software; Isso porque a versão de avaliação expira em 180 dias após a instalação. No entanto, você não precisará desinstalar completamente a versão de avaliação e instalar a versão licenciada. Em vez disso, após obter uma chave de licenciamento válida, você pode atualizar a versão de avaliação do Lync Server 2013 executando o procedimento a seguir em cada computador que atua como um servidor front-end do Lync Server, diretor ou servidor de borda. Observe que você não precisa atualizar os computadores que executam outras funções de servidor, como um servidor de monitoramento ou um servidor de arquivamento.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Atualização da versão de avaliação do Microsoft Lync Server 2013

Para atualizar um computador da versão de avaliação do Lync Server 2013 para a versão licenciada do software:

**Atualização da versão de avaliação do Microsoft Lync Server 2013**

1.  Faça logon no computador como um administrador local.

2.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Observe que talvez seja necessário especificar o caminho completo para o File Server. msi. Esse arquivo pode ser encontrado na pasta de instalação dos arquivos de instalação de mídia de volume do Lync Server.

4.  Após a conclusão da execução da instalação, digite o seguinte no prompt de comando e pressione ENTER:
    
        Enable-CsComputer

5.  Repita esse procedimento em qualquer outro servidor front-end, diretor ou servidor de borda executando uma cópia de avaliação do Lync Server. Esse procedimento também deve ser executado em qualquer servidor de filial do Office que tenha sido implantado usando os arquivos de instalação de mídia do Lync Server.

Se você não tem certeza se a versão de avaliação do Lync Server está em execução em um determinado computador, você pode verificar se está executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsServerVersion

O cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analisará o computador local e reportará um dos seguintes procedimentos:

  - Se a chave de licença de volume do Lync Server foi instalada no computador, o que significa que nenhuma atualização é necessária.

  - Se a chave de licença de avaliação do Lync Server foi instalada, o que significa que o computador deve ser atualizado.

  - Que nenhuma chave de licença de volume é necessária no computador. A atualização da versão de avaliação para a versão licenciada só é necessária em servidores front-end, directors e servidores Edge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

