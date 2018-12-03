---
title: Configurar o servidor de mediação
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar o servidor de mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico modificado em:** 28-09-2012_

Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do Office Communications Server 2007 R2 servidor de mediação herdado.

Para publicar com êxito, habilitar ou desabilitar uma topologia quando a adição ou remoção de uma função de servidor, você deve estar logado como um usuário que seja membro dos grupos RTCUniversalServerAdmins e administradores de domínio. Também é possível delegar os direitos de administrador e permissões para adicionar funções de servidor. Para obter detalhes, consulte Delegate Setup Permissions o servidor Standard Edition ou Enterprise Edition documentação de implantação. Para outras alterações de configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.

<div>


> [!NOTE]  
> Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, IP-PBXs e serviços de tronco SIP que funcionam com o Lync Server 2013, consulte "Microsoft Unified Communications programa de interoperabilidade aberta" em <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar o servidor de mediação usando o construtor de topologia

1.  Abra uma topologia existente no construtor de topologias.

2.  No painel esquerdo, navegue até **gateways PSTN**.

3.  Clique com o botão **gateways PSTN**e clique em **Novo Gateway IP/PSTN**.

4.  Preencha a página **Definir Novo Gateway IP/PSTN** com as seguintes informações:
    
      - Digite o FQDN ou endereço IP do gateway. O FQDN do gateway é necessário se o gateway usa o protocolo TLS.
    
      - Aceite o valor padrão da **porta de escuta para gateway IP/PSTN** ou insira a nova porta de escuta se ela foi modificada.
    
      - Defina o **protocolo de transporte de Sip**.

5.  No painel esquerdo, navegue até o **pool de Front End do Enterprise Edition** ou **Standard Edition Server**.

6.  Com o botão direito do pool e, em seguida, clique em **Editar propriedades**.

7.  Em **Servidor de mediação**, defina as **portas de escuta**.

8.  Em seguida, associe o gateway PSTN recém-criado, selecionando-o e clicando em **Adicionar**.

9.  No **Construtor de topologias**, selecione o nó superior **Lync Server**.

10. No menu **ação** , selecione **Publicar topologia** e, em seguida, clique em **Avançar**.

11. Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente.

<div>


> [!NOTE]  
> É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rotas de voz de alteração para usar o servidor de mediação do Lync Server 2013 novo</A> para garantir que as rotas de voz estejam apontando para o servidor de mediação correto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

