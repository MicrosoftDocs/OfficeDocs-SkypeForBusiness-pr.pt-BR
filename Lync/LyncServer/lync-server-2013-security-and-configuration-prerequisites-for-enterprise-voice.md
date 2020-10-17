---
title: Pré-requisitos de segurança e configuração para o Enterprise Voice
description: Pré-requisitos de segurança e configuração para o Enterprise Voice.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0940450889c6bf26cb7761bebbce5e6c2d3f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551467"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2bb1b-103">Pré-requisitos de segurança e configuração para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bb1b-103">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bb1b-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2bb1b-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2bb1b-105">Verifique se a sua infraestrutura atende aos seguintes pré-requisitos de segurança, configuração do usuário e hardware específico ao cenário.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-105">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="2bb1b-106">Direitos Administrativos e Infraestrutura do Certificado</span><span class="sxs-lookup"><span data-stu-id="2bb1b-106">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="2bb1b-107">Certifique-se que o ambiente está configurado com os grupos de usuários administrativos e infraestrutura de certificado para o uso durante o processo de implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-107">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="2bb1b-108">Os administradores responsáveis pela implantação do Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="2bb1b-109">Administradores realizando as tarefas de configuração devem ter direitos adequados:</span><span class="sxs-lookup"><span data-stu-id="2bb1b-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="2bb1b-110">**CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="2bb1b-p101">**CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="2bb1b-113">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2bb1b-114">A delegação permite que mais administradores participem da sua implantação do Lync Server sem abrir o acesso desnecessário aos recursos.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-114">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="2bb1b-115">A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-115">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2bb1b-116">Para obter detalhes sobre os requisitos de certificado no Lync Server, consulte <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate Infrastructure Requirements for Lync server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-116">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="2bb1b-117">Configuração do usuário</span><span class="sxs-lookup"><span data-stu-id="2bb1b-117">User Configuration</span></span>

<span data-ttu-id="2bb1b-118">Se você colocar o servidor de mediação com cada pool de front-ends ou servidor Standard Edition durante a implantação de front end, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-118">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="2bb1b-119">Se você estiver recém implantando a carga de trabalho do Enterprise Voice, antes de iniciar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-119">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="2bb1b-120">Como administrador, você é responsável por certificar-se que esse número seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-120">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="2bb1b-121">Antes da implementação, todos os números de telefone principais devem ser normalizados (formatados corretamente) e copiados para a propriedade **URI de linha** de cada usuário usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-121">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2bb1b-122">Para obter exemplos de números de telefone principais necessários para a implantação do Enterprise Voice, consulte a seção <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync server 2013</A> de <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-122">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="2bb1b-123">Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN</span><span class="sxs-lookup"><span data-stu-id="2bb1b-123">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="2bb1b-124">Depois de verificar os pré-requisitos de software e de ambiente para o Enterprise Voice, você pode usar o conteúdo a seguir para:</span><span class="sxs-lookup"><span data-stu-id="2bb1b-124">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="2bb1b-125">Instale o servidor de mediação, conforme descrito em [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas somente se você deseja implantar um servidor de mediação autônomo ou pool porque os servidores de mediação são instalados como parte do processo de implantação do servidor de front-end ou Standard Edition quando colocado.</span><span class="sxs-lookup"><span data-stu-id="2bb1b-125">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="2bb1b-126">Ou, comece a definir as configurações para rotear chamadas para usuários do Enterprise Voice, conforme descrito em [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="2bb1b-126">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

