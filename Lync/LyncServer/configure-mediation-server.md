---
title: Configurar o servidor de mediação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389c6e5c017594bf386109541a379bd5ae2f7e01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurar o servidor de mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do servidor herdado do Office Communications Server 2007 R2.

Para publicar com sucesso, habilite ou desabilite uma topologia ao adicionar ou remover uma função do servidor, você deve estar conectado como um usuário que é um membro do RTCUniversalServerAdmins e dos grupos Administradores do Domínio. Também é possível delegar os direitos e as permissões de administrador corretos para  adicionar funções do do servidor. Para obter detalhes, consulte Permissões de configuração delegadas na Documentação de implantação do servidor Standard Edition ou servidor Enterprise Edition. Para obter as alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é exigida.

<div>


> [!NOTE]  
> Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, IP-PBXs e serviços de tronco SIP que funcionam com o Lync Server 2013, consulte "programa de interoperabilidade aberta <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>da comunicação unificada da Microsoft" em.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Para configurar o Servidor de Mediação usando o Construtor de Topologias

1.  Abra uma topologia existente no Construtor de Topologias.

2.  No painel esquerdo, navegue até **Gateways PSTN**.

3.  Clique com o botão direito nos **Gateways PSTN** e, clique em **Novo Gateway IP/PSTN**.

4.  Complete a página **Definir Novo Gateway IP/PSTN** com as seguintes informações:
    
      - Insira o FQDN do gateway ou endereço IP. O FQDN do gateway é exigido se o gateway utiliza o protocolo TLS.
    
      - Aceite o valor padrão do **Porta de Escuta do Gateway IP/PSTN** ou insira a nova porta de escuta se ela for modificada.
    
      - Defina o **Protocolo de Transporte SIP**.

5.  No painel esquerdo, navegue até o **Pool de Front-Ends Enterprise Edition** ou o **Servidor Standard Edition**.

6.  Clique com o botão direito no pool e, em seguida, clique em **Editar propriedades**.

7.  Em **Servidor de Mediação**, defina as **Portas de Escuta**.

8.  Em seguida, associe o gateway PSTN mais recente criado, o selecionando e clicando em **Adicionar**.

9.  Em **Construtor de Topologias**, selecione o nó superior do **Lync Server**.

10. No menu **Ação**, selecione **Publicar Topologia** e clique em **Avançar**.

11. Quando o **Assistente para Publicação** for concluído, clique em **Concluir ** para fechar o assistente.

<div>


> [!NOTE]  
> É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">altere as rotas de voz para usar o novo servidor de mediação do Lync Server 2013</A> para garantir que as rotas de voz estejam apontando para o servidor de mediação correto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

