---
title: Fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo (opcional)
description: Fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo (opcional).
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559417"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo (opcional)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Use o procedimento a seguir para fazer a transição do seu Servidor de Mediação, colocado no seu servidor Standard Edition ou no pool de Front-Ends, para um Servidor de Mediação autônomo para uma implantação em um único local.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Para mudar um Servidor de Mediação colocado para um Servidor de Mediação autônomo

1.  Abrir uma topologia existente do Topology Builder.

2.  No painel à esquerda, navegue até **Pools de mediação**.

3.  Clique com o botão direito em **Pools de mediação** e selecione **Novo Servidor de Mediação**.

4.  Na página **Definir Novo Pool de Mediação**, forneça o FQDN do novo pool do Servidor de Mediação. Selecione também se este será um pool de servidor único ou de vários servidores e clique em **Avançar**.

5.  Selecione o pool do próximo salto do servidor Front-End para o qual no novo Servidor de Mediação roteará chamadas de entrada e clique em **Avançar**.

6.  Selecione o pool de Borda a ser usado pelo Servidor de Mediação e clique em **Avançar**.

7.  Na página **Especificar gateways PSTN**, associe o gateway PSTN anterior ao Servidor de Mediação. Selecione o gateway e clique em **Adicionar**.

8.  Clique em **Concluir** para fechar o assistente **Definir Novo Pool de Mediação**.

9.  No **Construtor de topologias**, selecione o nó superior **Lync Server 2013**.

10. No painel **Ações**, selecione **Publicar Topologia** e conclua o assistente.

11. Siga as etapas em [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) na documentação de implantação para instalar os arquivos no novo servidor de mediação.

12. Depois que os arquivos estiverem instalados no Servidor de Mediação, volte para o Construtor de Topologias e, no painel à esquerda, navegue até o pool.

13. Clique com o botão direito no pool e selecione **Editar Propriedades**.

14. Sob **Servidor de Mediação**, desmarque a opção **Servidor de Mediação posicionado habilitado** e clique em **OK**.

15. No **Construtor de topologias**, selecione o nó superior **Lync Server 2013**.

16. No menu **Ação**, selecione **Publicar Topologia** e conclua o assistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

