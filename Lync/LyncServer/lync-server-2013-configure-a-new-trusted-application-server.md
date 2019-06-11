---
title: 'Lync Server 2013: configurar um novo servidor de aplicativos confiável'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurar um novo servidor de aplicativos confiável no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft UCMA (Microsoft Unified Communications Managed) 3,0 Core SDK que é confiável para o Microsoft Lync Server 2013. Para obter detalhes sobre aplicativos do UCMA, consulte "documentação do SDK do 3,0 Core Communications [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)Managed API" em.

Para obter informações sobre como configurar o Microsoft Outlook Web Access (OWA) e o Lync Server 2013, consulte "configurar o Outlook Web App e o Lync Server 2010 Integration" na documentação do Microsoft Exchange Server 2013.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. Também é possível delegar as permissões e direitos de administrador adequados para adicionar funções de servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação. Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Para configurar um servidor de aplicativos confiável

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

3.  Selecione **baixar topologia da implantação existente**e, em seguida, clique em **OK**.

4.  Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologias que você deseja usar e, em seguida, clique em **salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e, em seguida, clique em **novo pool de aplicativos confiável**.

6.  Digite o **FQDN do pool** do pool de aplicativos confiáveis, selecione se ele será um único servidor ou vários servidores e clique em **Avançar**.

7.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-end do Lync Server 2013.

8.  Clique em **Concluir**.

9.  Selecione o nó superior do **Lync Server 2013**e, em seguida, no menu **ações** , clique em **publicar topologia**.
    
    O **pool de aplicativos confiável** deve ter sido criado com êxito e associado ao pool de front-end correto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

