---
title: Verificar ambiente do Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Verificar ambiente do Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Antes de implantar o Lync Server 2013 em um estado de coexistência com o Lync Server 2010, você precisa verificar se os serviços do Lync Server 2010 foram configurados e iniciados. É importante identificar os principais serviços e recursos que existem em seu ambiente herdado antes de implantar um pool piloto do Lync Server 2013. Antes de implantar o Microsoft Lync Server 2013 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identifica qual parceiro federado a configuração de XMPP herdada tem suporte. A verificação da implantação do Lync Server 2010 herdada envolve o seguinte:

  - Verificando se os serviços do Lync Server 2010 foram iniciados

  - Revisão da topologia e dos usuários no Lync Server 2010.

  - Verificar as configurações do servidor de Federação e de borda.

  - Verificar os serviços do XMPP e os parceiros federados.

**Verificar se os serviços do Lync Server 2010 foram iniciados**

1.  No servidor de front-end do Lync Server 2010, navegue até o\\applet Serviços de ferramentas administrativas.

2.  Verifique se os seguintes serviços estão em execução no servidor front-end:
    
    ![Lista de serviços em execução no front-end Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de serviços em execução no front-end Server")

**Examine a topologia do Lync Server 2010 no painel de controle do Lync Server**

1.  Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.

2.  Abra o painel de controle do Lync Server.

3.  Selecione **topologia**. Verifique se os vários servidores na sua implantação do Lync Server 2010 estão listados.
    
    ![Página de topologia do painel de controle do Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topologia do painel de controle do Lync Server 2010")

**Para revisar os usuários do Lync Server 2010 no painel de controle do Lync Server**

1.  Abra o painel de controle do Lync Server.

2.  Selecione **usuários** e, em seguida, clique em **Localizar**.

3.  Verifique se a coluna **pool de registradores** aponta para o pool do Lync Server 2010 para cada usuário listado.
    
    ![Painel de controle do Lync Server 2010 listando usuários](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Painel de controle do Lync Server 2010 listando usuários")

**Para verificar as configurações de borda e Federação do Lync Server 2010**

1.  Iniciar o construtor de topologias.

2.  Selecione **baixar a topologia na implantação existente**.

3.  Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.

4.  Expanda o nó do Lync Server 2010 para revelar as várias funções de servidor na implantação.

5.  Selecione o nó do site e verifique se um valor de **atribuição de roteiro de Federação do site** está definido.
    
    ![Construtor de topologias, roteiro de Federação do site](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Construtor de topologias, roteiro de Federação do site")

6.  Em seguida, selecione o servidor Standard Edition ou o pool Front-end da edição Enterprise. Determine se um pool de bordas foi configurado para mídia abaixo de **associações**.
    
    ![Construtor de topologias mostrando servidores e pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Construtor de topologias mostrando servidores e pools")

7.  Por fim, selecione o pool de bordas e identifique se um próximo pool de saltos está configurado abaixo da **próxima seleção de salto**.
    
    ![Construtor de topologias, seleção do próximo salto](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Construtor de topologias, seleção do próximo salto")

**Verificar a configuração de parceiro federado do XMPP herdado**

1.  No servidor herdado XMPP, navegue até o applet Serviços\\de ferramentas administrativas.

2.  Verifique se o serviço do Gateway XMPP do Office Communications Server foi iniciado.
    
    ![Serviço de Gateway XMPP do Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Serviço de Gateway XMPP do Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

