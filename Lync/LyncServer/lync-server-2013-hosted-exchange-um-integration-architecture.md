---
title: 'Lync Server 2013: arquitetura de integração do UM do Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2c16350ff111f31eb52a73290b1dbcddc9e580
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512578"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Arquitetura de integração do UM do Exchange hospedada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

O aplicativo de roteamento ExUM do Lync Server 2013 oferece suporte à integração com uma implantação de um (Unificação de mensagens) do Exchange no local, com um do Exchange hospedado por um provedor de serviços ou com uma combinação dos dois. O diagrama abaixo mostra todas as três possibilidades.

**Integração com implantação de UM do Exchange local e dois provedores Exchange hospedados**

![Implantação de UM do Exchange do Lync Server local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")

Os modos a seguir são suportados:

  - **Implantação local:** O Lync Server 2013 e o Exchange UM são implantados em servidores locais dentro de sua empresa.

  - **Implantação entre locais:** O Lync Server 2013 é implantado em servidores locais dentro de sua empresa e o UM do Exchange é hospedado em um recurso do provedor de serviços online, como um data center do Microsoft Exchange Online.

  - **Implantação mista:** Sua implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais do Exchange dentro da sua empresa e algumas caixas de correio hospedadas em um data center de serviço do Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > A implantação mista pode ser usada como uma solução de transição durante a avaliação e migração em fases de usuários ao UM do Exchange hospedado, ou uma solução permanente caso você opte por manter alguns serviços de UM do Exchange dos usuários no local, após transferir outros.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Espaço de Endereçamento SIP Compartilhado

Para integrar o Lync Server 2013 a uma implantação local do UM do Exchange, conceda a permissão do Lync Server 2013 para ler os objetos dos serviços de domínio do Active Directory da UM do Exchange. Essa abordagem não funciona para integração com a UM do Exchange hospedada, no entanto, porque o Lync Server 2013 e o Exchange UM estão instalados em florestas separadas sem nenhuma confiança entre elas.

Para integrar o Lync Server 2013 à UM do Exchange hospedado, você deve configurar um *espaço de endereçamento SIP compartilhado*. Nessa configuração, o mesmo espaço de endereço de domínio SIP está disponível para o Lync Server 2013 e para o provedor de serviço UM do Exchange hospedado.

<div>


> [!NOTE]  
> O uso do espaço de endereçamento SIP compartilhado é semelhante à abordagem usada em um ambiente do Lync Server 2013 entre locais, em que alguns usuários estão hospedados na implantação local e alguns estão hospedados em uma implantação hospedada (como o Lync Online). O domínio SIP está dividido entre eles. Ao integrar o Lync Server 2013 com o Exchange UM hospedado, certifique-se de incluir o provedor de serviços UM do Exchange no espaço de endereçamento SIP compartilhado.



</div>

Para configurar o espaço de endereço SIP compartilhado para integrar-se com um provedor de serviço UM do Exchange, você deve configurar seu Servidor de Borda como exemplificado a seguir:

1.  Configure o Servidor de Borda para federação, executando o cmdlet **Set-CsAccessEdgeConfiguration** para definir os seguintes parâmetros:
    
      - **UseDnsSrvRouting** especifica que Servidores de Borda dependerão de registros SRV DNS quando estiverem enviando ou recebendo solicitações de federação.
    
      - **AllowFederatedUsers** especifica se os usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em uma situação de divisão de domínios.
    
      - **EnablePartnerDiscovery** especifica se o Lync Server 2013 usará registros DNS para tentar descobrir domínios de parceiros que não estão listados na lista de domínios permitidos do Active Directory. Se for falso, o Lync Server 2013 se federará apenas com domínios encontrados na lista de domínios permitidos. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS. Na maioria das implantações, o valor é definido como falso para evitar abrir a federação a todos os parceiros.

2.  Replique o repositório de gerenciamento central para o servidor de borda e verifique a replicação. Para obter detalhes, consulte [exportar sua topologia do Lync Server 2013 e copiá-lo para mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) na documentação de implantação.

3.  Configure um *provedor de hospedagem* no Servidor de Borda, executando o cmdlet **New-CsHostingProvider** para configurar os seguintes parâmetros:
    
      - **Identidade** especifica um identificador de valor de string único para o provedor de hospedagem que você está criando, por exemplo, **UM do Exchange Hospedado**.
    
      - **Ativado** indica se a conexão de rede entre o seu domínio e o provedor de hospedagem está ativa. Deve ser **Verdadeiro**.
    
      - **EnabledSharedAddressSpace**indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Deve ser **Verdadeiro**.
    
      - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Lync Server 2013. Deve ser **Falso**.
    
      - **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem, por exemplo, **proxyserver.fabrikam.com**. Entre em contato com seu provedor de hospedagem por esta informação. Este valor não pode ser modificado. Se o provedor de hospedagem mudar seu servidor proxy, você precisará excluir e então recriar o registro para aquele provedor.
    
      - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Lync Server 2013. Deve ser **Falso**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

