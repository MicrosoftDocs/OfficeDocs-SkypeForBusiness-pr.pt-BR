---
title: Processo de atualização de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Saiba como o cliente de desktop equipes é atualizado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829092"
---
# <a name="teams-update-process"></a><span data-ttu-id="99401-103">Processo de atualização de equipes</span><span class="sxs-lookup"><span data-stu-id="99401-103">Teams update process</span></span>

<span data-ttu-id="99401-104">O aplicativo da Web de equipes é atualizado semanal.</span><span class="sxs-lookup"><span data-stu-id="99401-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="99401-105">Atualizações de cliente de desktop equipes sejam liberadas cada duas semanas após rigorosos testes internos e validação por meio de nosso programa de adoção de tecnologia (toque).</span><span class="sxs-lookup"><span data-stu-id="99401-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="99401-106">Isso geralmente ocorre em uma terça-feira.</span><span class="sxs-lookup"><span data-stu-id="99401-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="99401-107">Se uma atualização crítica for necessária, equipes irá ignorar essa agenda e liberar a atualização assim que estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="99401-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="99401-108">Cliente de desktop do próprio atualiza automaticamente.</span><span class="sxs-lookup"><span data-stu-id="99401-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="99401-109">Verificações de equipes para atualiza cada poucas horas em segundo plano, a baixa e aguarda até que o computador ficar ocioso antes silenciosamente instalando a atualização.</span><span class="sxs-lookup"><span data-stu-id="99401-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="99401-110">Os usuários podem baixar também manualmente as atualizações ao clicar em **Verificar se há atualizações** no menu suspenso de **perfil** no canto superior direito do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="99401-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="99401-111">Se houver uma atualização disponível, ele será baixado e instalado silenciosamente quando o computador estiver ocioso.</span><span class="sxs-lookup"><span data-stu-id="99401-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="99401-112">Os usuários precisam estar conectado para atualizações sejam baixados.</span><span class="sxs-lookup"><span data-stu-id="99401-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="99401-113">E sobre atualizações do Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="99401-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="99401-114">As equipes é instalado por padrão com as novas instalações do Office 365 ProPlus, conforme descrito em [Implantar equipes da Microsoft com o Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="99401-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="99401-115">As equipes segue seu próprio processo de atualização, conforme descrito acima e não o processo de atualização para os outros aplicativos de escritórios, como Word e Excel.</span><span class="sxs-lookup"><span data-stu-id="99401-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="99401-116">E quanto a atualizações a equipes de VDI?</span><span class="sxs-lookup"><span data-stu-id="99401-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="99401-117">Clientes de equipes em Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente a maneira que os clientes não - VDI equipes.</span><span class="sxs-lookup"><span data-stu-id="99401-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="99401-118">Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito nas instruções para [Instalar equipes em VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="99401-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="99401-119">Você deve desinstalar a versão atual para atualizar para uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="99401-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="99401-120">Pode admins implantar as atualizações em vez de equipes atualização automática?</span><span class="sxs-lookup"><span data-stu-id="99401-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="99401-121">As equipes não dá admins a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.</span><span class="sxs-lookup"><span data-stu-id="99401-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
