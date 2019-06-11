---
title: 'Lync Server 2013: Arquitetura de integração do UM do Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Arquitetura de integração do UM do Exchange hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-25_

O aplicativo de roteamento ExUM do Lync Server 2013 dá suporte à integração com uma implantação do Exchange Unified Messaging (UM) local, com um provedor de serviços do Exchange hospedado por um provedor de serviços ou com uma combinação dos dois. O diagrama a seguir mostra todas as três possibilidades.

**Integração com uma implantação do Exchange UM local e dois provedores do Exchange hospedados**

![Implantação do Exchange um do Lync Server local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação do Exchange um do Lync Server local")

Há suporte para os seguintes modos:

  - **Implantação local:** O Lync Server 2013 e o Exchange UM são implantados em servidores locais dentro da sua empresa.

  - **Implantação em várias instalações:** O Lync Server 2013 é implantado em servidores locais na sua empresa e o Exchange UM está hospedado em um recurso do provedor de serviços online, como um Data Center online do Microsoft Exchange.

  - **Implantação mista:** A implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais do Exchange na sua empresa e algumas caixas de correio hospedadas em um data center do serviço do Exchange.
    
    <div>
    

    > [!NOTE]  
    > A implantação mista pode ser usada como uma solução de transição durante a avaliação e a migração em fases de usuários para o Exchange UM hospedada ou uma solução permanente se você optar por manter os serviços de UM dos usuários do Exchange no local depois de transferir outras pessoas.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espaço de endereço SIP compartilhado

Para integrar o Lync Server 2013 com uma implantação do Exchange UM local, conceda a permissão do Lync Server 2013 para ler objetos dos serviços de domínio do Active Directory de UM Exchange. No entanto, essa abordagem não funciona para a integração com o Exchange UM hospedado, porque o Lync Server 2013 e o Exchange UM são instalados em florestas separadas sem nenhuma confiança entre elas.

Para integrar o Lync Server 2013 com o Exchange UM hospedado, você deve configurar um *espaço de endereço SIP compartilhado*. Nesta configuração, o mesmo espaço de endereço de domínio SIP está disponível para o Lync Server 2013 e para o provedor de serviços de UM host do Exchange.

<div>


> [!NOTE]  
> O uso do espaço de endereço SIP compartilhado é semelhante à abordagem usada em um ambiente do Lync Server 2013, no qual alguns usuários são hospedados na implantação local e alguns são hospedados em uma implantação hospedada (como o Lync Online). O domínio SIP é dividido entre eles. Ao integrar o Lync Server 2013 com o Exchange UM hospedado, certifique-se de incluir o provedor de serviços de UM do Exchange no espaço de endereço SIP compartilhado.



</div>

Para configurar o espaço de endereço SIP compartilhado para integração com um provedor de serviços de UM Exchange, você precisa configurar o servidor de borda da seguinte maneira:

1.  Configure o servidor de borda para Federação executando o cmdlet **set-CsAccessEdgeConfiguration** para definir os seguintes parâmetros:
    
      - **UseDnsSrvRouting ** especifica se os Servidores de Borda dependerão dos registros DNS SRV ao enviar e receber solicitações de federação.
    
      - **AllowFederatedUsers ** especifica se os usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em uma situação de divisão de domínios.
    
      - **EnablePartnerDiscovery** especifica se o Lync Server 2013 usará os registros de DNS para tentar descobrir domínios de parceiros que não estão listados na lista de domínios permitidos do Active Directory. Se falso, o Lync Server 2013 se federará apenas com domínios encontrados na lista de domínios permitidos. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS. Na maioria das implantações, o valor é definido como falso para evitar abrir a federação a todos os parceiros.

2.  Replique o repositório de gerenciamento central para o servidor de borda e verifique a replicação. Para obter detalhes, consulte [exportar sua topologia do Lync Server 2013 e copiá-la para mídia externa para instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) na documentação de implantação.

3.  Configure um *provedor de hospedagem* no servidor de borda executando o cmdlet **New-CsHostingProvider** para definir os seguintes parâmetros:
    
      - **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando, por exemplo, **Hosted Exchange um**.
    
      - **Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Deve ser definido como **true**.
    
      - **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereçamento SIP compartilhado. Deve ser definido como **true**.
    
      - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Lync Server 2013. Deve ser definido como **false**.
    
      - **ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) do servidor proxy usado pelo provedor de hospedagem, por exemplo, **ProxyServer.fabrikam.com**. Entre em contato com seu provedor de hospedagem para obter essas informações. Esse valor não pode ser modificado. Se o provedor de hospedagem alterar seu servidor proxy, será preciso excluir e recriar a entrada para esse provedor.
    
      - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na sua topologia do Lync Server 2013. Deve ser definido como **false**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

