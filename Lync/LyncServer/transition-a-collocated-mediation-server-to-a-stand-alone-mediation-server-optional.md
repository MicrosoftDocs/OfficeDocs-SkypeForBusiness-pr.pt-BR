---
title: Fazer a transição de um servidor de mediação posicionado para um servidor autônomo de mediação (opcional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c6a76bceb935900521859911ce5398ae2213e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Fazer a transição de um servidor de mediação posicionado para um servidor autônomo de mediação (opcional)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Use o procedimento a seguir para fazer a transição do servidor de mediação, posicionado no seu servidor Standard Edition ou no pool Front-end, em um servidor autônomo de mediação para uma implantação de um único site.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Para fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo

1.  Abra uma topologia existente do construtor de topologias.

2.  No painel esquerdo, navegue até **pools de mediação**.

3.  Clique com o botão direito em **pools de mediação** e selecione **novo servidor de mediação**.

4.  Na página **definir novo pool de mediação** , forneça o FQDN do novo pool do servidor de mediação. Além disso, selecione se este pool será um pool de servidor único ou de vários servidores e clique em **Avançar**.

5.  Selecione o pool do servidor front-end de salto seguinte para o qual o novo servidor de mediação roteará chamadas de entrada e clique em **Avançar**.

6.  Selecione o pool de bordas a ser usado pelo servidor de mediação e clique em **Avançar**.

7.  Na página **especificar gateways PSTN** , associe o gateway PSTN anterior ao servidor de mediação. Selecione o gateway e clique em **Adicionar**.

8.  Clique em **concluir** para fechar o assistente para **definir novo pool de mediação** .

9.  No **Construtor de topologias**, selecione o nó superior do **Lync Server 2013**.

10. No painel **ações** , selecione **publicar topologia** e conclua o assistente.

11. Siga as etapas em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) na documentação de implantação para instalar os arquivos no novo servidor de mediação.

12. Após a instalação dos arquivos no servidor de mediação, retorne ao construtor de topologias e, no painel esquerdo, navegue até o pool.

13. Clique com o botão direito do mouse no pool e selecione **Editar propriedades**.

14. Em **servidor de mediação**, desmarque a caixa de seleção **posicionada no servidor de mediação posicionado** e clique em **OK**.

15. No **Construtor de topologias**, selecione o nó superior do **Lync Server 2013**.

16. No menu **ação** , selecione **publicar topologia** e conclua o assistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

