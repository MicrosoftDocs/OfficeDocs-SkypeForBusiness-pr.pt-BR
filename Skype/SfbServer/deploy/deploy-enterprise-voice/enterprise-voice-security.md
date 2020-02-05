---
title: Pré-requisitos de configuração e segurança do Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumo: Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767234"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="cf494-103">Pré-requisitos de configuração e segurança do Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cf494-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="cf494-104">**Resumo:** Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf494-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="cf494-105">Antes de implantar o Enterprise Voice, verifique se a sua infraestrutura atende aos seguintes pré-requisitos de segurança, configuração do usuário e hardware específico do cenário.</span><span class="sxs-lookup"><span data-stu-id="cf494-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="cf494-106">Direitos Administrativos e Infraestrutura do Certificado</span><span class="sxs-lookup"><span data-stu-id="cf494-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="cf494-107">Antes de implantar, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf494-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="cf494-108">Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf494-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="cf494-109">Administradores realizando as tarefas de configuração devem ter direitos adequados:</span><span class="sxs-lookup"><span data-stu-id="cf494-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="cf494-110">**CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="cf494-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="cf494-p101">**CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.</span><span class="sxs-lookup"><span data-stu-id="cf494-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="cf494-113">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf494-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="cf494-114">A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.</span><span class="sxs-lookup"><span data-stu-id="cf494-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf494-115">Para obter detalhes sobre os requisitos de certificado no Skype for Business Server, consulte [requisitos ambientais para requisitos de servidor do Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [do Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf494-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="cf494-116">Configuração do usuário</span><span class="sxs-lookup"><span data-stu-id="cf494-116">User configuration</span></span>

<span data-ttu-id="cf494-117">Se você colocar o servidor de mediação em cada pool de front-end ou servidor Standard Edition durante a implantação de front-end, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="cf494-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="cf494-118">Se você estiver implantando a carga de trabalho de Enterprise Voice no momento, antes de começar o processo de implantação, designe um número de telefone principal para cada usuário que você planeja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cf494-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="cf494-119">Como administrador, você é responsável por certificar-se que esse número seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="cf494-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="cf494-120">Antes da implementação, todos os números de telefone primários devem ser normalizados (formatados corretamente) e copiados para cada propriedade de **URI de linha** do usuário usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf494-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf494-121">Para obter exemplos dos números de telefone principais necessários para a implantação do Enterprise Voice, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="cf494-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="cf494-122">Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN</span><span class="sxs-lookup"><span data-stu-id="cf494-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="cf494-123">Depois de verificar o software e os pré-requisitos ambientais do Enterprise Voice, você pode:</span><span class="sxs-lookup"><span data-stu-id="cf494-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="cf494-124">Instale o servidor de mediação, conforme descrito em [implantar um servidor de mediação no construtor de topologias no servidor do Skype for Business](deploy-a-mediation-server.md), mas somente se você quiser implantar um servidor ou pool autônomo de mediação, pois os servidores de mediação são instalados como parte do processo de implantação do servidor do front-end ou da edição padrão quando posicionado.</span><span class="sxs-lookup"><span data-stu-id="cf494-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="cf494-125">Ou comece a definir as configurações para direcionar as chamadas para usuários do Enterprise Voice, conforme descrito em [Configurar troncos no Skype for Business Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="cf494-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

