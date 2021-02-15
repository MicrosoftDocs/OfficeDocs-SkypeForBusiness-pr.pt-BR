---
title: Exibir definições de configuração de reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir as definições de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827921"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="77e1d-103">Exibir definições de configuração de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77e1d-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="77e1d-104">**Resumo:** Saiba como exibir as definições de configuração de reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77e1d-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="77e1d-105">Você pode exibir as definições de configuração de reunião usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77e1d-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77e1d-106">Exibir definições de configuração de reunião usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77e1d-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="77e1d-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="77e1d-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="77e1d-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="77e1d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="77e1d-109">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="77e1d-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77e1d-110">Na barra de navegação esquerda, clique **em Conferência e** em Configuração de **Reunião.**</span><span class="sxs-lookup"><span data-stu-id="77e1d-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="77e1d-111">Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="77e1d-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="77e1d-112">Em **Editar Filtro de Arquivo,** marque a caixa de seleção **Mostrar** Detalhes.</span><span class="sxs-lookup"><span data-stu-id="77e1d-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="77e1d-113">**Editar Configuração \<policy\> de Reunião -** abre exibindo as configurações da política selecionada.</span><span class="sxs-lookup"><span data-stu-id="77e1d-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="77e1d-114">Para obter detalhes sobre como definir as configurações, consulte Criar definições de [configuração de reunião no Skype for Business Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="77e1d-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77e1d-115">Exibir definições de configuração de reunião usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="77e1d-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="77e1d-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="77e1d-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="77e1d-117">Para exibir informações sobre todas as definições de configuração de reunião, use o cmdlet **Get-CsMeetingConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="77e1d-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="77e1d-118">Este comando retornará informações semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="77e1d-118">This command will return information similar to the following:</span></span>
  
<pre>
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
</pre>

<span data-ttu-id="77e1d-119">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77e1d-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

