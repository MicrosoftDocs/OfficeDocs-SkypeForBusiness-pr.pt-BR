---
title: Pré-requisitos de configuração e segurança para Entreprise Voice no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Resumo: Aprenda sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server 2015.'
ms.openlocfilehash: 2ece3aaa99c1e81afd9241e8d435ac0ab3328893
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="5cd20-103">Pré-requisitos de configuração e segurança para Entreprise Voice no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5cd20-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5cd20-104">**Resumo:** Saiba mais sobre os pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5cd20-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5cd20-105">Antes de implantar o Enterprise Voice, verifique se sua infraestrutura atende a seguir de segurança, configuração do usuário e os pré-requisitos de hardware específico ao cenário.</span><span class="sxs-lookup"><span data-stu-id="5cd20-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="5cd20-106">Direitos Administrativos e Infraestrutura do Certificado</span><span class="sxs-lookup"><span data-stu-id="5cd20-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="5cd20-107">Antes de implantar, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5cd20-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="5cd20-108">Os administradores a implantar o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5cd20-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="5cd20-109">Administradores realizando as tarefas de configuração devem ter direitos adequados:</span><span class="sxs-lookup"><span data-stu-id="5cd20-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="5cd20-110">**CsVoiceAdministrator:** Essa função de administrador pode realizar as tarefas de configuração de voz, gerenciar os aplicativos de voz e designar as políticas de voz aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="5cd20-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="5cd20-p101">**CsUserAdministrator:** Essa função de administrador pode gerenciar as propriedades do usuário, como habilitar o Enterprise Voice para um usuário, pode designar políticas por usuário, com exceção da política de arquivamento, além de mover usuários e gerenciar telefones de área comum e dispositivos análogos.</span><span class="sxs-lookup"><span data-stu-id="5cd20-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="5cd20-113">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator e do CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5cd20-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="5cd20-114">A infraestrutura de chave gerenciada (MKI) é implantada e configurada, usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de um terceiro.</span><span class="sxs-lookup"><span data-stu-id="5cd20-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cd20-115">Para obter detalhes sobre os requisitos de certificado do Skype para Business Server, consulte [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd20-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="5cd20-116">Configuração do usuário</span><span class="sxs-lookup"><span data-stu-id="5cd20-116">User configuration</span></span>

<span data-ttu-id="5cd20-117">Se você tiver colocado o servidor de mediação com cada pool de Front-End ou servidor Standard Edition durante a implantação de Front-End, as configurações de usuário necessárias para o Enterprise Voice foram configuradas automaticamente durante a instalação dos arquivos para essas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="5cd20-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="5cd20-118">Se você estiver implantando o a carga de trabalho do Enterprise Voice recentemente neste momento, antes de começar o processo de implantação, designe um número de telefone principal de cada usuário que você planeja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5cd20-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="5cd20-119">Como administrador, você é responsável por certificar-se que esse número seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="5cd20-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="5cd20-120">Antes da implementação, principal de todos os números devem ser normalizados telefone (formatados corretamente) e copiado para a propriedade **URI da linha** de cada usuário usando Skype para painel de controle do Business Server.</span><span class="sxs-lookup"><span data-stu-id="5cd20-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5cd20-121">Para obter exemplos dos números de telefone principais necessários para a implantação do Enterprise Voice, consulte [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="5cd20-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="5cd20-122">Próximas etapas: Instalar arquivos ou configurar a conectividade da PSTN</span><span class="sxs-lookup"><span data-stu-id="5cd20-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="5cd20-123">Depois de verificar os pré-requisitos de ambiente para o Enterprise Voice e software você pode:</span><span class="sxs-lookup"><span data-stu-id="5cd20-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="5cd20-124">Instalar o servidor de mediação, conforme descrito em [implantar um servidor de mediação no construtor de topologia no Skype para Business Server 2015](deploy-a-mediation-server.md), mas somente se você deseja implantar um servidor de mediação autônomo ou um pool porque os servidores de mediação são instalados como parte da frente Encerrar o pool ou o processo de implantação do Standard Edition server quando colocado.</span><span class="sxs-lookup"><span data-stu-id="5cd20-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="5cd20-125">Ou então, iniciar a configuração para rotear chamadas para usuários do Enterprise Voice, conforme descrito em [Configure troncos no Skype para Business Server 2015](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="5cd20-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server 2015](configure-trunks.md).</span></span>
    

