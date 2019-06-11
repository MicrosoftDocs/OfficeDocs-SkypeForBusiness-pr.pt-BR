---
title: 'Lync Server 2013: Instalando o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="80f20-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80f20-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80f20-103">_**Tópico da última modificação:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="80f20-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="80f20-104">Você pode baixar o portal da Web administrativo do sistema de sala do Microsoft Lync no centro [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)de download da Microsoft em.</span><span class="sxs-lookup"><span data-stu-id="80f20-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="80f20-105">Para instalar o portal da Web administrativo do sistema de salas do Lync, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="80f20-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="80f20-106">Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="80f20-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="80f20-107">Para instalar o portal da sala de reunião, baixe o **LyncRoomAdminPortal. exe** e, em seguida, execute-o como administrador.</span><span class="sxs-lookup"><span data-stu-id="80f20-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="80f20-108">Abra o arquivo Web. config do seguinte local:</span><span class="sxs-lookup"><span data-stu-id="80f20-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="80f20-109">% Arquivos de programa\\% Microsoft Lync Server\\2013 Web\\Components do\\Portal\\de sala de reunião do portal de sala de reunião</span><span class="sxs-lookup"><span data-stu-id="80f20-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="80f20-110">No arquivo Web. config, altere a PortalUserName para o nome de usuário criado na etapa 2 na seção "Configurando pré-requisitos para o portal de administração do sistema de salas do Lync" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="80f20-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="80f20-111">Como o portal de administração do LRS é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="80f20-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="80f20-112">Se esse usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="80f20-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="80f20-113">Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="80f20-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="80f20-114">Verificando a instalação do portal da Web administrativo do sistema de salas do Lync</span><span class="sxs-lookup"><span data-stu-id="80f20-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="80f20-115">Para verificar a instalação do portal da Web administrativo do sistema de salas do Lync, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80f20-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="80f20-116">Em um servidor front-end, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="80f20-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="80f20-117">https://\<FE-servidor\>/lRS</span><span class="sxs-lookup"><span data-stu-id="80f20-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="80f20-118">Você não verá nenhum erro, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="80f20-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="80f20-119">![Tela de entrada do portal de administração do sistema de salas do Lync] (images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="80f20-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="80f20-120">Se você não vir nenhum erro, tente acessar a seguinte URL a partir de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="80f20-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="80f20-121">https://\<FE-servidor\>/lRS</span><span class="sxs-lookup"><span data-stu-id="80f20-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="80f20-122">Para acessar a página, você precisará adicionar os registros DNS conforme descrito em "registros de DNS necessários para a entrada automática do cliente" em [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span><span class="sxs-lookup"><span data-stu-id="80f20-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

