---
title: 'Aplicativo pacientes para administradores do teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Aplicativo pacientes para administradores do teams
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749553"
---
# <a name="patients-app-overview"></a><span data-ttu-id="e08cc-103">Visão geral do aplicativo de pacientes</span><span class="sxs-lookup"><span data-stu-id="e08cc-103">Patients app overview</span></span>

<span data-ttu-id="e08cc-104">O aplicativo pacientes é um aplicativo do Microsoft Teams Store disponível para todos os usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="e08cc-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="e08cc-105">O aplicativo permite que as equipes de atendimento ao paciente que consistem em funcionários clínicos (por exemplo, retomadas, médicos, colegas de trabalho sociais) podem auxiliar e revisar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares da equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="e08cc-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="e08cc-106">O aplicativo tem dois modos:</span><span class="sxs-lookup"><span data-stu-id="e08cc-106">The app has two modes:</span></span> 

- <span data-ttu-id="e08cc-107">O modo conectado do EMR que se conecta ao EMRs por meio do FHIR.</span><span class="sxs-lookup"><span data-stu-id="e08cc-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="e08cc-108">O aplicativo modo conectado do EMR permanece em uma visualização privada e clientes interessados ou administradores podem solicitar acesso ao aplicativo, descartando um email da Microsoft no teamsforhealthcare@service.microsoft.com com informações sobre o locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e08cc-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="e08cc-109">O modo manual que permite às equipes de cuidado adicionar/trazer as informações do paciente manualmente.</span><span class="sxs-lookup"><span data-stu-id="e08cc-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="e08cc-110">O aplicativo está disponível na loja de aplicativos do teams para que os usuários finais baixem por padrão e estejam em visualização pública.</span><span class="sxs-lookup"><span data-stu-id="e08cc-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="e08cc-111">O aplicativo pode ser restrito a determinadas seções de usuários usando [políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e08cc-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="e08cc-112">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="e08cc-112">Usage example</span></span>

<span data-ttu-id="e08cc-113">Durante as sessões de arredondamento em cada mudança de médico, os clínicos reúnem-se na estação Nursing para discutir as atualizações mais recentes sobre o andamento com os pacientes.</span><span class="sxs-lookup"><span data-stu-id="e08cc-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="e08cc-114">Elas destacam as principais métricas críticas (não necessariamente médicas ou que se encontram explícitas nos registros médicos dos pacientes) e garantem que o paciente esteja no caminho deslizante certo para a descarga eletrostática com base em seu diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e08cc-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="e08cc-115">Para arredondar esses pacientes, a enfermeira de cobrança define o aplicativo paciente em uma equipe em que todos os clínicos são adicionados e adiciona pacientes a uma lista de pacientes.</span><span class="sxs-lookup"><span data-stu-id="e08cc-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="e08cc-116">Durante os rodadas, as minhas mãos e os outros responsáveis pelos participantes do paciente acessarem o Microsoft Teams e o aplicativo pacientes em seus dispositivos móveis e atualizarão as informações relevantes dos pacientes em seus dispositivos e, em seguida, todos os outros na equipe de atendimento podem ver essas atualizações e anotações e Fique em sincronia. Duas vezes por dia, no início e no final de um turno, eles também têm reuniões de equipe displicinary para passar pela lista de pacientes e usar o aplicativo pacientes para se basear e compartilhar informações sobre cada paciente usando o aplicativo pacientes em uma tela grande de exibição.</span><span class="sxs-lookup"><span data-stu-id="e08cc-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="e08cc-117">Muitas vezes, alguns clínicos também podem discar para essas reuniões de equipes remotamente e ainda fazer parte da discussão.</span><span class="sxs-lookup"><span data-stu-id="e08cc-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="e08cc-118">Configurar o aplicativo pacientes</span><span class="sxs-lookup"><span data-stu-id="e08cc-118">Configure Patients app</span></span>

<span data-ttu-id="e08cc-119">Para obter informações sobre como preparar seu ambiente para usar o aplicativo pacientes do modo EMR, consulte [integrando registros eletrônicos de saúde ao Microsoft Teams](patients-app.md).</span><span class="sxs-lookup"><span data-stu-id="e08cc-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="e08cc-120">Você também precisará ver [gerenciar políticas de configuração do aplicativo no Microsoft Teams](../../teams-app-setup-policies.md) para habilitar o aplicativo pacientes para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e08cc-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="e08cc-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e08cc-121">Related topics</span></span>

[<span data-ttu-id="e08cc-122">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e08cc-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
