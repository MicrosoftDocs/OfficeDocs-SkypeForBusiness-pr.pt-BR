---
title: 'Lync Server 2013: problemas com o teste de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemas com o teste de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Assim como o cmdlet **Test-CsTopology** , o analisador de práticas recomendadas fornece uma maneira de verificar se o Lync Server 2013 está funcionando corretamente em um nível global. Por padrão, o analisador de práticas recomendadas, como o cmdlet, verifica toda a infraestrutura do Lync Server 2013, verificando se os serviços necessários estão em execução e se as permissões e os direitos de usuário adequados foram definidos para esses serviços e para o universal grupos de segurança criados quando você instala o Lync Server 2013.

Além de verificar a validade do Lync Server como um todo, o **Test-CsTopology** também verifica a validade de um serviço específico. Para obter detalhes sobre como usar o cmdlet para testar serviços específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) na documentação do Shell de gerenciamento do Lync Server. Use as informações a seguir para ajudar a solucionar problemas com a sua topologia.

<div>


> [!NOTE]  
> Dependendo da configuração dos seus servidores de borda e das configurações de rede de perímetro relacionadas, incluindo configurações de firewall e permissões, o analisador de práticas recomendadas pode não conseguir acessar e examinar seus servidores de borda. Se você incluir servidores de borda na digitalização e os relatórios indicarem que há um problema ao acessar os servidores de borda, desmarque a caixa de seleção <STRONG>servidores de borda</STRONG> e execute a digitalização novamente para impedir que o problema apareça nos relatórios.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Solucionando problemas com a sua topologia

Se o teste de topologia encontrar problemas com a sua topologia, esses problemas provavelmente são causados por problemas que ocorreram quando você publicou ou habilitou sua topologia.

Quando você faz alterações na sua topologia, as alterações só entram em vigor quando foram publicadas e habilitadas. Você deve usar o construtor de topologias para fazer alterações de topologia. Depois de fazer as alterações, você pode publicar e habilitar essas alterações usando o construtor de topologias.

Quando você publica as alterações, as novas informações (por exemplo, um novo site ou uma nova função de servidor) são gravadas no repositório de gerenciamento central. No entanto, esses objetos novos (ou os recém modificados) não se unem imediatamente à sua topologia. Os objetos entram em sua topologia somente quando você habilita a topologia atualizada. Se você selecionar a opção publicar no construtor de topologia, essas duas etapas ocorrerão: as alterações serão publicadas (isto é, serão gravadas no repositório de gerenciamento central) e a nova topologia será habilitada.

Por padrão, os membros do grupo RTCUniversalServerAdmins são autorizados a executar o cmdlet **Publish-CsTopology** e o cmdlet **Enable-CsTopology** . No entanto, se as permissões de configuração não tiverem sido delegadas, você deverá estar conectado como um administrador de domínio para executar **Publish-CsTopology**. Para dar à RTCUniversalServerAdmins o direito de realmente usar o cmdlet **Publish-CsTopology** , você deve executar o cmdlet **Grant-CsSetupPermission** em cada contêiner do Active Directory que contém computadores que executam serviços do Lync Server. Para dar à RTCUniversalServerAdmins o direito de usar o cmdlet **Enable-CsTopology** , você deve executar o cmdlet **set-CsSetupPermission** em todos os contêineres de serviços de domínio Active Directory que contenham computadores executando os serviços do Lync Server. Observe que isso se aplica à habilitação e publicação de uma topologia usando o construtor de topologias. Se você não tiver delegado permissões usando **set-CsSetupPermission**, apenas um administrador de domínio poderá habilitar e publicar uma topologia por meio do construtor de topologias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

