---
title: 'Lync Server 2013: instalar o portal da Web administrativo do sistema de salas do Lync'
description: 'Lync Server 2013: instalar o portal da Web administrativo do sistema de salas do Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fba239346d75142bb4009c58e0ac67e8e1f3bcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573867"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="cfae0-103">Instalando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfae0-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfae0-104">_**Última modificação do tópico:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="cfae0-104">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="cfae0-105">Você pode baixar o portal da Web administrativo do sistema de salas do Microsoft Lync no centro de download da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) .</span><span class="sxs-lookup"><span data-stu-id="cfae0-105">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="cfae0-106">Para instalar o portal da Web administrativo do sistema de salas do Lync, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="cfae0-106">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="cfae0-107">Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="cfae0-107">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="cfae0-108">Para instalar o portal de sala de reunião, baixe **LyncRoomAdminPortal.exe** e, em seguida, execute-o como administrador.</span><span class="sxs-lookup"><span data-stu-id="cfae0-108">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="cfae0-109">Abra o arquivo Web.config do seguinte local:</span><span class="sxs-lookup"><span data-stu-id="cfae0-109">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="cfae0-110">% Arquivos de programa% \\ Microsoft Lync Server 2013 manipulador de \\ sala de reunião de Web Components \\ int do portal \\ </span><span class="sxs-lookup"><span data-stu-id="cfae0-110">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\\\

4.  <span data-ttu-id="cfae0-111">No arquivo Web.Config, altere o PortalUserName para o nome de usuário criado na etapa 2, abaixo da seção "Configurando pré-requisitos para o portal de administração do sistema de salas do Lync" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="cfae0-111">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="cfae0-112">Como o portal de administração do LRS é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="cfae0-112">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="cfae0-113">Se este usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo de Web.Config:</span><span class="sxs-lookup"><span data-stu-id="cfae0-113">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="cfae0-114">Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web.Config:</span><span class="sxs-lookup"><span data-stu-id="cfae0-114">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="cfae0-115">Verificando a instalação do portal da Web administrativo do sistema de salas do Lync</span><span class="sxs-lookup"><span data-stu-id="cfae0-115">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="cfae0-116">Para verificar a instalação do portal da Web administrativo do sistema de salas do Lync, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cfae0-116">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="cfae0-117">Em um servidor front-end, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="cfae0-117">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="cfae0-118">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="cfae0-118">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="cfae0-119">Você não verá nenhum erro, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="cfae0-119">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="cfae0-120">![Tela de entrada do portal de administração do sistema de salas do Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="cfae0-120">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="cfae0-121">Se você não vir nenhum erro, tente acessar a seguinte URL de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="cfae0-121">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="cfae0-122">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="cfae0-122">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="cfae0-123">Para acessar a página, você precisará adicionar os registros DNS, conforme descrito em "registros de DNS necessários para entrada automática de cliente" em [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) .</span><span class="sxs-lookup"><span data-stu-id="cfae0-123">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

