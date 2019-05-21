---
title: Exibir informações de configuração de CDR no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumo: saiba como usar a CDR (gravação de detalhes de chamadas) no Skype for Business Server.'
ms.openlocfilehash: e0aed0c26672b83cb223ba763eb6224025d68118
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279645"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="75c39-103">Exibir informações de configuração de CDR no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="75c39-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="75c39-104">**Resumo:** Saiba como usar a CDR (gravação de detalhes de chamadas) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="75c39-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="75c39-p101">O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="75c39-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="75c39-107">Quando você instala o Skype for Business Server, uma única coleção global de definições de configuração de CDR é criada para você.</span><span class="sxs-lookup"><span data-stu-id="75c39-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="75c39-108">Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="75c39-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="75c39-109">Você pode exibir as configurações de CDR em uso em sua organização usando o painel de controle do Skype for Business Server ou o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="75c39-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="75c39-110">Para exibir as informações de configuração de CDR usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="75c39-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="75c39-111">No painel de controle do Skype for Business Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="75c39-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="75c39-p103">Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.</span><span class="sxs-lookup"><span data-stu-id="75c39-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75c39-115">Exibindo informações de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75c39-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="75c39-116">Você pode exibir as configurações de configuração de CDR usando o Windows PowerShell e o cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="75c39-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="75c39-117">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75c39-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75c39-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="75c39-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="75c39-119">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="75c39-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="75c39-120">Para visualizar informações de configuração do CDR</span><span class="sxs-lookup"><span data-stu-id="75c39-120">To view CDR configuration information</span></span>

- <span data-ttu-id="75c39-121">Para ver as informações sobre todas as suas configurações de CDR, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="75c39-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="75c39-122">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="75c39-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="75c39-123">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="75c39-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

