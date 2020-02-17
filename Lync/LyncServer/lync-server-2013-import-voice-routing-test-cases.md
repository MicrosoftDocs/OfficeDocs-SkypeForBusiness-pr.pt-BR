---
title: 'Lync Server 2013: importar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bb5d8e8f29edf0397c9bb9fa12592087ea517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importar casos de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Os casos de teste fornecem uma maneira de testar as rotas de voz em sua organização: você define coisas como o número a ser discado e o plano de discagem e a política de voz a serem empregados, e o Lync Server 2013 pode então verificar se, dadas essas condições, o número fornecido pode succes sfully ser roteado para a rede PSTN.

Os casos de teste, que podem ser criados usando o painel de controle do Lync Server, são normalmente salvos somente no servidor onde o caso foi originalmente criado e executado. No entanto, esses casos de teste podem ser exportados como arquivos XML (com a extensão. vtest) e importados em outros servidores. Isso permite que você execute os mesmos testes em computadores diferentes localizados em diferentes pontos da sua topologia.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>Para importar um caso de teste de roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz**.

4.  No menu **ações** , clique em **importar casos de teste**.

5.  Localize o arquivo de caso de teste (. vtest) que você deseja importar e clique em **abrir**.

6.  Clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que você importa um arquivo. vtest, deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar o caso de teste. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira Também


[Exportar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

