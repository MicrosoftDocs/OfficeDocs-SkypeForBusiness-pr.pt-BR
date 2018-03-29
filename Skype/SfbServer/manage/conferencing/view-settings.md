---
title: Exibir definições de configuração de reuniões no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir configurações de reunião no Skype para Business Server 2015.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="58757-103">Exibir definições de configuração de reuniões no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="58757-103">View meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58757-104">**Resumo:** Saiba como exibir configurações de reunião no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="58757-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="58757-105">Você pode exibir configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="58757-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="58757-106">Exibir configurações de reunião usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="58757-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="58757-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="58757-107"></span></span>

1. <span data-ttu-id="58757-108">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="58757-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="58757-109">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="58757-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="58757-110">Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="58757-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="58757-111">Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="58757-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="58757-112">Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="58757-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="58757-113">**Editar configuração de reunião - \<política\> ** abre exibindo as configurações para a política selecionada.</span><span class="sxs-lookup"><span data-stu-id="58757-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="58757-114">Para obter detalhes sobre como definir as configurações, consulte [criar definições de configuração do Skype para Business Server 2015 da reunião](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="58757-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server 2015](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="58757-115">Exibir configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="58757-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="58757-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="58757-116"></span></span>

<span data-ttu-id="58757-117">Para visualizar informações sobre todas as definições de configurações de reunião, use o cmdlet **Get-CsMeetingConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="58757-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="58757-118">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="58757-118">This command will return information similar to the following:</span></span>
  
```
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True

```

<span data-ttu-id="58757-119">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="58757-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

