---
title: 'Lync Server 2013: visão geral do ambiente híbrido do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0594ddc0433bdcc227c693c4842c08bf7d05989f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="4eafe-102">Visão geral do ambiente híbrido do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eafe-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eafe-103">_**Tópico da última modificação:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="4eafe-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="4eafe-104">O ambiente híbrido do Lync Server 2013 refere-se a uma implantação na qual há alguns usuários hospedados no Lync Server local 2013 e outros usuários em casa ao Lync Online, mas os usuários compartilham o mesmo domínio, como user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4eafe-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="4eafe-105">Sobre este guia</span><span class="sxs-lookup"><span data-stu-id="4eafe-105">About this Guide</span></span>

<span data-ttu-id="4eafe-106">Este guia descreve as tarefas necessárias para configurar seu ambiente do Lync Server 2013 para interoperabilidade com o Lync Online e, em seguida, para mover os usuários da sua implantação local para usar o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4eafe-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="4eafe-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4eafe-107">Prerequisites</span></span>

<span data-ttu-id="4eafe-108">Você precisará ter os seguintes aplicativos e utilitários instalados para concluir as tarefas de configuração de uma implantação para híbrido.</span><span class="sxs-lookup"><span data-stu-id="4eafe-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="4eafe-109">Os instaladores desses arquivos estão incluídos na mídia de instalação fornecida para a sua implantação, bem como nos links incluídos na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="4eafe-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="4eafe-110">Serviços de Federação do Active Directory (AD FS) 2,0</span><span class="sxs-lookup"><span data-stu-id="4eafe-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="4eafe-111">Ferramenta de sincronização de diretórios da Microsoft 9,1</span><span class="sxs-lookup"><span data-stu-id="4eafe-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="4eafe-112">Instalar o Windows PowerShell para logon único com o AD FS</span><span class="sxs-lookup"><span data-stu-id="4eafe-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="4eafe-113">O assistente de conexão do Microsoft Online Services (msoidcli-7.0. msi) está incluído na configuração da área de trabalho do Office 365, que pode ser obtida na página de downloads vinculada a partir do portal de administração do 365 do Office.</span><span class="sxs-lookup"><span data-stu-id="4eafe-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="4eafe-114">Credenciais de administrador</span><span class="sxs-lookup"><span data-stu-id="4eafe-114">Administrator Credentials</span></span>

<span data-ttu-id="4eafe-115">Quando for solicitado a fornecer as credenciais de administrador, use o nome de usuário e a senha da conta de administrador para o seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4eafe-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="4eafe-116">Você também usará essas credenciais ao configurar o AD FS (serviços de Federação do Active Directory) 2,0, a sincronização de diretórios, o logon único, a Federação e a transferência de usuários para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4eafe-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="4eafe-117">Conectando-se ao Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eafe-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="4eafe-118">Os administradores agora têm a capacidade de usar o Windows PowerShell para gerenciar o Lync Online e suas contas de usuário do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4eafe-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="4eafe-119">Para fazer isso, primeiro você deve baixar e instalar o módulo do conector do Lync Online a partir do centrohttp://go.microsoft.com/fwlink/?LinkId=294688)de download da Microsoft (.</span><span class="sxs-lookup"><span data-stu-id="4eafe-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="4eafe-120">Para obter mais informações sobre como baixar, instalar e usar o módulo conector do Lync Online e obter informações detalhadas sobre como usar o Windows PowerShell para gerenciar o Lync Online, consulte [usando o Windows PowerShell para gerenciar o Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4eafe-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

