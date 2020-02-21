---
title: 'Lync Server 2013: protegendo e protegendo servidores e aplicativos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8de372a8ca0ae6ec8c80a147eb74ffb01d0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="d67b9-102">Proteção e proteção de servidores e aplicativos para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67b9-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67b9-103">_**Última modificação do tópico:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="d67b9-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="d67b9-104">Você deve aumentar a segurança do sistema operacional e dos aplicativos de acordo com as práticas recomendadas para esse componente específico.</span><span class="sxs-lookup"><span data-stu-id="d67b9-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="d67b9-105">Esta seção descreve como proteger os servidores de aplicativo e usar a Política de Grupo para implementar os bloqueios de segurança.</span><span class="sxs-lookup"><span data-stu-id="d67b9-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d67b9-106">Você também pode proteger e proteger os bancos de dados usados para a implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d67b9-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="d67b9-107">Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">proteção e proteção dos bancos de dados do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d67b9-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="d67b9-108">Protegendo servidores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d67b9-108">Securing Application Servers</span></span>

<span data-ttu-id="d67b9-p103">No caso dos servidores de aplicativos, a segurança do sistema operacional e do aplicativo deve ser intensificada. Por exemplo, um computador com o Windows Server 2008 dedicado à execução do ISA (Microsoft Internet Security and Acceleration) Server 2006 deve ser protegido sob a perspectiva do sistema operacional e do aplicativo. Minimizar o número de serviços em execução e fornecidos pelo servidor deve ser a meta principal.</span><span class="sxs-lookup"><span data-stu-id="d67b9-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="d67b9-112">Protegendo servidores virtuais</span><span class="sxs-lookup"><span data-stu-id="d67b9-112">Securing Virtual Servers</span></span>

<span data-ttu-id="d67b9-113">Os instantâneos de servidores virtuais contêm cópias dos discos de dados do servidor e também contém despejos de dados na memória, que podem conter dados criptografados confidenciais que estão sujeitos a ataques.</span><span class="sxs-lookup"><span data-stu-id="d67b9-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="d67b9-114">Para os servidores de produção implementados usando a virtualização, você deve desabilitar todos os instantâneos de servidor ou gerenciá-los de maneira muito controlada.</span><span class="sxs-lookup"><span data-stu-id="d67b9-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="d67b9-115">Para obter detalhes sobre como proteger servidores virtuais do Hyper-V, consulte o guia de segurança do Hyper [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)-v em:.</span><span class="sxs-lookup"><span data-stu-id="d67b9-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="d67b9-116">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="d67b9-116">Group Policy</span></span>

<span data-ttu-id="d67b9-p105">No Windows Server 2008 e no Windows Server 2008 R2, a Política de Grupo fornece gerenciamento da configuração de área de trabalho baseado em diretório. Você pode usar a Política de Grupo para implementar os bloqueios de segurança, definindo as configurações do Computador e Usuário dentro de um GPO (objeto de Política de Grupo) para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d67b9-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="d67b9-119">Políticas baseadas no Registro</span><span class="sxs-lookup"><span data-stu-id="d67b9-119">Registry-based policies</span></span>

  - <span data-ttu-id="d67b9-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="d67b9-120">Security</span></span>

  - <span data-ttu-id="d67b9-121">Instalação de software</span><span class="sxs-lookup"><span data-stu-id="d67b9-121">Software installation</span></span>

  - <span data-ttu-id="d67b9-122">Scripts</span><span class="sxs-lookup"><span data-stu-id="d67b9-122">Scripts</span></span>

  - <span data-ttu-id="d67b9-123">Redirecionamento de pasta</span><span class="sxs-lookup"><span data-stu-id="d67b9-123">Folder redirection</span></span>

  - <span data-ttu-id="d67b9-124">Serviços de instalação remota</span><span class="sxs-lookup"><span data-stu-id="d67b9-124">Remote installation services</span></span>

<span data-ttu-id="d67b9-125">Para fornecer uma interface de usuário para o administrador configurar essas configurações, os modelos administrativos são fornecidos com versões de sistema operacional, versões de Service Pack e alguns aplicativos, incluindo o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d67b9-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="d67b9-126">O arquivo Communicator. adm é um modelo administrativo que acompanha o Lync Server 2013, é instalado no diretório% windir%\\inf\\ e fornece uma interface para as configurações da política de grupo.</span><span class="sxs-lookup"><span data-stu-id="d67b9-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="d67b9-127">Cada configuração no Communicator.adm corresponde a uma configuração do Registro que afeta o comportamento do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d67b9-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="d67b9-128">As configurações podem ser acessadas no GPedit.dll, que, por sua vez, está disponível no console Usuários e Computadores do Active Directory e no GPMC (Console de Gerenciamento de Diretiva de Grupo).</span><span class="sxs-lookup"><span data-stu-id="d67b9-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="d67b9-129">Configurações de segurança de Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="d67b9-129">Group Policy Security Settings</span></span>

<span data-ttu-id="d67b9-130">A Política de Grupo contém as configurações de segurança de um GPO em Configuração do Computador/Configurações do Windows/Configurações de Segurança quando é acessada a partir do GPedit.dll.</span><span class="sxs-lookup"><span data-stu-id="d67b9-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="d67b9-131">Você pode importar os modelos de segurança para definir as configurações de segurança do GPO.</span><span class="sxs-lookup"><span data-stu-id="d67b9-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="d67b9-132">O guia de segurança do Windows Server [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 2008 em e o kit de ferramentas de gerenciamento de conformidade [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) de segurança do Windows Server 2008 R2 contêm vários exemplos de modelos que podem ser modificados para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="d67b9-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="d67b9-133">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="d67b9-133">Best Practices</span></span>

  - <span data-ttu-id="d67b9-134">Melhore a segurança de todos os sistemas operacionais e aplicativos do servidor.</span><span class="sxs-lookup"><span data-stu-id="d67b9-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="d67b9-135">Proteja os instantâneos de servidor e aumente a segurança de todos os servidores virtuais.</span><span class="sxs-lookup"><span data-stu-id="d67b9-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="d67b9-136">Use a Política de Grupo para implementar os bloqueios de segurança.</span><span class="sxs-lookup"><span data-stu-id="d67b9-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

