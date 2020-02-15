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
ms.openlocfilehash: 254fb591acca4f58bf27b300d5ead3e615e026ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemas com o teste de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Como o cmdlet **Test-CsTopology** , o analisador de práticas recomendadas oferece uma maneira de verificar se o Lync Server 2013 está funcionando corretamente em um nível global. Por padrão, o analisador de práticas recomendadas, como o cmdlet, verifica toda a sua infraestrutura do Lync Server 2013, verificando se os serviços necessários estão em execução e se os direitos e permissões de usuário adequados foram definidos para esses serviços e para o universal grupos de segurança criados quando você instala o Lync Server 2013.

Além de verificar a validade do Lync Server como um todo, o **Test-CsTopology** também verifica a validade de um serviço específico. Para obter detalhes sobre como usar o cmdlet para testar serviços específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) na documentação do Shell de gerenciamento do Lync Server. Use as informações a seguir para ajudar a resolver problemas com sua topologia.

<div>


> [!NOTE]  
> Dependendo da configurçaão de seus servidores de borda e quasquer definições de rede de perímetro relacionada, incluindo de firewall e permissões, o Analisar de Práticas Recomendadas pode não conseguir acessar e escanear seus servidores de borda. Se incluir servidores de borda no escaneamento e os relatórios indicarem que há um problema no acesso aos servidores de borda, remova a seleção da caixa <STRONG>Servidores de Borda</STRONG> e execute o scan novamente para evitar que o problema conste nos relatórios.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Resolver problemas com sua topologia

Se o teste de topologia encontrar problemas com sua topologia, esses problemas são provavelmente causados por problemas que ocorreram quando você publicou ou habilitou sua topologia.

Ao fazer modificações em sua topologia, elas entrarão em efeito somente quando forem publicadas e habilitadas. Você deve usar o construtor de topologias para fazer alterações na topologia. Após fazer as alterações, você pode publicar e habilitar essas alterações usando o construtor de topologias.

Quando você publica as alterações, as novas informações (por exemplo, um novo site ou uma nova função de servidor) são gravadas no repositório de gerenciamento central. Contudo, esses novos (ou recém-modificados) objetos não entrarão imediatamente em sua topologia. Os objetivos entram em sua topologia somente quando você permite a atualização da topologia. Se você selecionar a opção publicar no construtor de topologia, essas duas etapas ocorrerão: as alterações serão publicadas (ou seja, serão gravadas no repositório de gerenciamento central) e, em seguida, a nova topologia será habilitada.

Por padrão, membros do grupo RTCUniversalServerAdmins estão autorizados a executar os cmdlets **Publish-CsTopology** e **Enable-CsTopology**. Contudo, se permissões de configuração não foram delegadas, você estar logado como administrador do domínio para executar **Publish-CsTopology**. Para dar ao RTCUniversalServerAdmins o direito de realmente usar o cmdlet **Publish-CsTopology** , você deve executar o cmdlet **Grant-CsSetupPermission** em todos os contêineres do Active Directory que contenham computadores executando os serviços do Lync Server. Para dar ao RTCUniversalServerAdmins o direito de usar o cmdlet **Enable-CsTopology** , você deve executar o cmdlet **set-CsSetupPermission** em todos os contêineres de serviços de domínio do Active Directory que contenham computadores que executam os serviços do Lync Server. Observe que isso se aplica à habilitação e publicação de uma topologia usando o construtor de topologias. Se você não tiver delegado permissões usando **set-CsSetupPermission**, somente um administrador de domínio poderá habilitar e publicar uma topologia por meio do construtor de topologias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

