---
title: 'Lync Server 2013: configurar um novo servidor de aplicativos confiáveis'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e053629eae42bc7fcd83b0002b3aad40f3550f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507708"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurar um novo servidor de aplicativos confiáveis no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Microsoft Lync Server 2013. Para obter detalhes sobre os aplicativos do UCMA, consulte "documentação do SDK básico do Unified Communications Managed API 3,0 em [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .

Para obter informações sobre como configurar o Microsoft Outlook Web Access (OWA) e o Lync Server 2013, consulte "configurar o Outlook Web App e o Lync Server 2010 Integration" na documentação do Microsoft Exchange Server 2013.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar um remover uma função do servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e de Administradores de Domínio. Também é possível delegar as permissões e direitos de administrador adequadas para adicionar funções do servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação. Para outras alterações na configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Para configurar um servidor de aplicativos confiáveis

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

3.  Selecione **Baixar topologia da implantação existente** e clique em **OK**.

4.  Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologia que você deseja usar e clique em **salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e clique em **novo pool de aplicativos confiáveis**.

6.  Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Lync Server 2013**e, no menu **ações** , clique em **publicar topologia**.
    
    O **pool de aplicativos confiáveis** deve ter sido criado com êxito e associado ao pool de front-ends correto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

