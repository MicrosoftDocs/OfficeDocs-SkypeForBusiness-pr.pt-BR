---
title: Configurar o servidor de mediação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar o servidor de mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do servidor herdado do Office Communications Server 2007 R2 Media Server.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. Também é possível delegar direitos e permissões de administrador adequadas para adicionar funções de servidor. Para obter detalhes, consulte delegar permissões de configuração na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server. Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.

<div>


> [!NOTE]  
> Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, PBXs IP e serviços de entroncamento SIP que funcionam com o Lync Server 2013, consulte "programa de interoperabilidade aberto da <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Microsoft Unified Communications" em.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar o servidor de mediação usando o construtor de topologias

1.  Abra uma topologia existente do construtor de topologias.

2.  No painel esquerdo, navegue até **gateways PSTN**.

3.  Clique com o botão direito do mouse em **gateways PSTN**e clique em **novo gateway IP/PSTN**.

4.  Conclua a página **definir o novo gateway IP/PSTN** com as seguintes informações:
    
      - Digite o endereço IP ou FQDN do gateway. O FQDN do gateway será necessário se o gateway usar o protocolo TLS.
    
      - Aceite o valor padrão da **porta de escuta do gateway IP/PSTN** ou digite a nova porta de escuta se ela tiver sido modificada.
    
      - Defina o **protocolo de transporte SIP**.

5.  No painel esquerdo, navegue até o **pool de front-end do Enterprise Edition** ou o **servidor Standard Edition**.

6.  Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

7.  Em **servidor**de mediação, defina as **portas de escuta**.

8.  Em seguida, associe o gateway PSTN recém-criado selecionando-o e clicando em **Adicionar**.

9.  Em **Construtor de topologia**, selecione o nó mais superior do **Lync Server**.

10. No menu **ação** , selecione **publicar topologia** e clique em **Avançar**.

11. Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.

<div>


> [!NOTE]  
> É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">altere as rotas de voz para usar o novo servidor de mediação do Lync server 2013</A> para garantir que as rotas de voz aponte para o servidor de mediação correto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

