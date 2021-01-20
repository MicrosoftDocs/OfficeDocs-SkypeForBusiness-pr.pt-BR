---
title: Informação de ITAdmin para cliente do Microsoft Teams para RealWear (visualização)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Apresentação de ITAdmin do cliente do Microsoft Teams para RealWear.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67f595e6b037eb6091d3b4e03e3258a13e12a4d1
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909385"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="94843-103">Microsoft Teams para RealWear</span><span class="sxs-lookup"><span data-stu-id="94843-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="94843-104">Este artigo aborda o cliente do Microsoft Teams para dispositivos portáteis RealWear.</span><span class="sxs-lookup"><span data-stu-id="94843-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="94843-105">Funcionários da linha de frente que usam o RealWear HMT-1 e HMT-1Z1 agora podem colaborar com um especialista remoto usando uma chamada de vídeo no Teams.</span><span class="sxs-lookup"><span data-stu-id="94843-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="94843-106">Por meio de uma interface de usuário controlada por voz, o Teams para RealWear permite que os funcionários de um campo permaneçam 100% com as mãos livres, enquanto mantêm a conscientização de situação em ambientes barulhentos e perigosos.</span><span class="sxs-lookup"><span data-stu-id="94843-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="94843-107">Ao mostrar o que eles veem em tempo real, os funcionários do campo podem acelerar o tempo para resolver problemas e reduzir o risco de um tempo de inatividade caro.</span><span class="sxs-lookup"><span data-stu-id="94843-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="94843-108">Como implantar o Microsoft Teams para RealWear</span><span class="sxs-lookup"><span data-stu-id="94843-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="94843-109">Dispositivos RealWear atualizados para versão 11.2 ou superior.</span><span class="sxs-lookup"><span data-stu-id="94843-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="94843-110">Saiba mais [aqui](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="94843-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="94843-111">Acesso a [RealWear Foresight](https://cloud.realwear.com/) para distribuição do cliente do Microsoft Teams for Realwear.</span><span class="sxs-lookup"><span data-stu-id="94843-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="94843-112">Licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="94843-112">Required Licenses</span></span>

<span data-ttu-id="94843-113">As licenças do Microsoft Teams fazem parte das assinaturas do Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="94843-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="94843-114">Nenhum licenciamento adicional é necessário para usar o Teams para RealWear.</span><span class="sxs-lookup"><span data-stu-id="94843-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="94843-115">Para saber mais sobre como obter o Teams, confira [Como faço para obter acesso ao Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="94843-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="94843-116">Gerenciar dispositivos RealWear</span><span class="sxs-lookup"><span data-stu-id="94843-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="94843-117">Gerenciador de pontos de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94843-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="94843-118">Dispositivos RealWear podem ser gerenciados usando o modo de administrador de dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="94843-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="94843-119">O suporte para gerenciamento via Android Enterprise é limitado, pois os dispositivos atualmente não têm o Google Mobile Services (GMS) disponível.</span><span class="sxs-lookup"><span data-stu-id="94843-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="94843-120">Para saber mais sobre como gerenciar dispositivos RealWear no Gerenciador de Pontos de Extremidade da Microsoft, confira [Registro de administrador de dispositivo Android no Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="94843-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="94843-121">Para obter mais detalhes sobre políticas, confira [Como usar o Intune em ambientes sem os Serviços do Google Mobile](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="94843-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="94843-122">Gerentes de Mobilidade Corporativa de Terceiros (EMMs)</span><span class="sxs-lookup"><span data-stu-id="94843-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="94843-123">Para obter instruções sobre a EMMs de terceiros, confira [Provedores de gerenciamento de mobilidade empresarial com suporte](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="94843-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="94843-124">Conteúdo do usuário final</span><span class="sxs-lookup"><span data-stu-id="94843-124">End-user content</span></span>

<span data-ttu-id="94843-125">Para obter mais informações sobre isso de uma perspectiva do usuário final, confira [Usando o Microsoft Teams para RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="94843-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
