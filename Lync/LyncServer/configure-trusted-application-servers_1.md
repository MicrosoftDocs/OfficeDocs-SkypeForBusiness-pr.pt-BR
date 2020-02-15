---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e74cba866a7353890bb47de745e5e525d43963
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurar os servidores de aplicativos confiáveis

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Em um ambiente misto, se você criar um novo servidor de aplicativos confiável após mesclar a topologia herdada do Office Communications Server com o Lync Server 2013 e definir um novo servidor de aplicativos confiável usando o construtor de topologias, você deve definir o próximo pool de salto como um Pool do Lync Server 2013. Em um ambiente mesclado, o pool herdado do Office Communications Server e o pool do Lync Server 2013 aparecem na lista suspensa. *Não* é permitido selecionar o pool herdado.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Para selecionar o Lync Server 2013 como próximo salto ao criar um servidor de aplicativos confiáveis

1.  Abra uma topologia existente no Construtor de Topologia.

2.  No painel à esquerda, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo pool de aplicativo confiável**.

3.  Insira o **Pool FQDN** para o pool de aplicativo confiável e selecione se será uma implantação de servidor único ou de vários servidores.

4.  Clique em **Avançar**.

5.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.
    
    ![Caixa de diálogo Definir novo pool de aplicativos confiáveis](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Caixa de diálogo Definir novo pool de aplicativos confiáveis")  

6.  Clique em **Concluir**.

7.  Selecione o nó superior **Servidor Lync** e, do painel **Ações**, selecione **Publicar**.

8.  Verifique se o **Pool de aplicativo confiável** foi criado com êxito e associado ao pool de Front End correto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

