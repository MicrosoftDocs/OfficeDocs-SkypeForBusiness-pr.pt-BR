---
title: Configurar servidores de aplicativo confiáveis
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
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicativo confiáveis

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Em um ambiente misto, se você criar um novo servidor de aplicativos confiável após mesclar a topologia herdada do Office Communications Server com o Lync Server 2013 e definir um novo servidor de aplicativos confiável usando o construtor de topologias, deverá definir o próximo pool de saltos como um Pool do Lync Server 2013. Em um ambiente mesclado, o pool herdado do Office Communications Server e o pool do Lync Server 2013 aparecem na lista suspensa. *Não* há suporte para a seleção do pool herdado.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Para selecionar o Lync Server 2013 como próximo nó ao criar um servidor de aplicativos confiável

1.  Abra uma topologia existente no construtor de topologias.

2.  No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis** e clique em **novo pool de aplicativos confiáveis**.

3.  Digite o **FQDN do pool** do pool de aplicativos confiável e selecione se ele será uma implantação de servidor único ou de vários servidores.

4.  Click **Next**.

5.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-end do Lync Server 2013.
    
    ![Caixa de diálogo Definir novo pool de aplicativos confiável](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Caixa de diálogo Definir novo pool de aplicativos confiável")  

6.  Clique em **Concluir**.

7.  Selecione o servidor de **Lync** do nó superior e, no painel **ações** , selecione **publicar**.

8.  Verifique se o **pool de aplicativos confiáveis** foi criado com êxito e associado ao pool de front-end correto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

