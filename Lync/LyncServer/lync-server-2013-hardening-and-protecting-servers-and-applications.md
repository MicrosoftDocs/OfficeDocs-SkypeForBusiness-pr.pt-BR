---
title: 'Lync Server 2013: Protegendo servidores e aplicativos'
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
ms.openlocfilehash: 42b8b9d3fc21c590bda12841cb6002987d4c0650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="441bc-102">Protegendo servidores e aplicativos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="441bc-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="441bc-103">_**Tópico da última modificação:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="441bc-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="441bc-104">Você deve proteger e proteger o sistema operacional e os aplicativos de acordo com as práticas recomendadas para esse componente específico.</span><span class="sxs-lookup"><span data-stu-id="441bc-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="441bc-105">Esta seção descreve como otimizar a segurança dos servidores de aplicativos e usar a política de grupo para implementar bloqueios de segurança.</span><span class="sxs-lookup"><span data-stu-id="441bc-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="441bc-106">Você também pode proteger e proteger os bancos de dados usados para a implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="441bc-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="441bc-107">Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">otimizando a proteção e protegendo os bancos de dados do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="441bc-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="441bc-108">Proteger servidores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="441bc-108">Securing Application Servers</span></span>

<span data-ttu-id="441bc-109">Para servidores de aplicativos, o sistema operacional e o aplicativo devem ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="441bc-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="441bc-110">Por exemplo, um computador com Windows Server 2008 dedicado a executar o Microsoft Internet Security and Acceleration (ISA) Server 2006 deve ser protegido do sistema operacional e da perspectiva do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="441bc-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="441bc-111">Minimizar o número de serviços em execução e fornecido pelo servidor deve ser um objetivo principal.</span><span class="sxs-lookup"><span data-stu-id="441bc-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="441bc-112">Protegendo servidores virtuais</span><span class="sxs-lookup"><span data-stu-id="441bc-112">Securing Virtual Servers</span></span>

<span data-ttu-id="441bc-113">Instantâneos do servidor virtual contêm cópias dos discos de dados do servidor e também contêm despejos de dados na memória, que podem conter dados de criptografia confidenciais que podem levar a ataques.</span><span class="sxs-lookup"><span data-stu-id="441bc-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="441bc-114">Para servidores de produção implementados usando a virtualização, você deve desabilitar todos os instantâneos do servidor ou gerenciá-los de forma bem controlada.</span><span class="sxs-lookup"><span data-stu-id="441bc-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="441bc-115">Para obter detalhes sobre como proteger servidores virtuais Hyper-V, consulte o guia de segurança do Hyper- [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)v em:.</span><span class="sxs-lookup"><span data-stu-id="441bc-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="441bc-116">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="441bc-116">Group Policy</span></span>

<span data-ttu-id="441bc-117">No Windows Server 2008 e no Windows Server 2008 R2, a política de grupo fornece o gerenciamento de configuração da área de trabalho baseado em diretório.</span><span class="sxs-lookup"><span data-stu-id="441bc-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="441bc-118">Você pode usar a política de grupo para implementar bloqueios de segurança definindo configurações de computador e de usuário em um objeto de política de grupo (GPO) para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="441bc-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="441bc-119">Políticas baseadas no registro</span><span class="sxs-lookup"><span data-stu-id="441bc-119">Registry-based policies</span></span>

  - <span data-ttu-id="441bc-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="441bc-120">Security</span></span>

  - <span data-ttu-id="441bc-121">Instalação do software</span><span class="sxs-lookup"><span data-stu-id="441bc-121">Software installation</span></span>

  - <span data-ttu-id="441bc-122">Escritas</span><span class="sxs-lookup"><span data-stu-id="441bc-122">Scripts</span></span>

  - <span data-ttu-id="441bc-123">Redirecionamento de pastas</span><span class="sxs-lookup"><span data-stu-id="441bc-123">Folder redirection</span></span>

  - <span data-ttu-id="441bc-124">Serviços de instalação remota</span><span class="sxs-lookup"><span data-stu-id="441bc-124">Remote installation services</span></span>

<span data-ttu-id="441bc-125">Para fornecer uma interface do usuário para o administrador definir essas configurações, os modelos administrativos são fornecidos com versões do sistema operacional, versões do Service Pack e alguns aplicativos, incluindo o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="441bc-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="441bc-126">O arquivo. adm do Communicator é um modelo administrativo que acompanha o Lync Server 2013, é instalado no diretório% windir\\%\\ inf e fornece uma interface para as configurações de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="441bc-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="441bc-127">Cada configuração no Communicator. adm corresponde a uma configuração no registro que afeta o comportamento do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="441bc-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="441bc-128">As configurações podem ser acessadas a partir de GPedit. dll, que está disponível no console usuários e computadores do Active Directory e no GPMC (console de gerenciamento de política de grupo).</span><span class="sxs-lookup"><span data-stu-id="441bc-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="441bc-129">Configurações de segurança de política de grupo</span><span class="sxs-lookup"><span data-stu-id="441bc-129">Group Policy Security Settings</span></span>

<span data-ttu-id="441bc-130">A política de grupo contém configurações de segurança para um GPO em configurações do computador/configurações do Windows/configurações de segurança quando acessado a partir do GPedit. dll.</span><span class="sxs-lookup"><span data-stu-id="441bc-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="441bc-131">Você pode importar modelos de segurança para definir configurações de segurança para o GPO.</span><span class="sxs-lookup"><span data-stu-id="441bc-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="441bc-132">O guia de segurança do Windows Server [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) 2008 em e o kit de ferramentas de gerenciamento de conformidade [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) de segurança do Windows Server 2008 R2 contém vários modelos de exemplo que você pode modificar para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="441bc-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="441bc-133">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="441bc-133">Best Practices</span></span>

  - <span data-ttu-id="441bc-134">Otimize a proteção de todos os sistemas operacionais e aplicativos do servidor.</span><span class="sxs-lookup"><span data-stu-id="441bc-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="441bc-135">Proteger os instantâneos do servidor e aprimorar a segurança de todos os servidores virtuais.</span><span class="sxs-lookup"><span data-stu-id="441bc-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="441bc-136">Use a política de grupo para implementar bloqueios de segurança.</span><span class="sxs-lookup"><span data-stu-id="441bc-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

