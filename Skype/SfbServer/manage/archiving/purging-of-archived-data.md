---
title: Gerenciar a purgação de dados arquivados no Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumo: Saiba como gerenciar a purgação de dados arquivados do Skype for Business Server.'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828531"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="910da-103">Gerenciar a purgação de dados arquivados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="910da-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="910da-104">**Resumo:** Saiba como gerenciar a purgação de dados arquivados para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="910da-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="910da-105">O banco de dados de Arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta de e-discovery (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento.</span><span class="sxs-lookup"><span data-stu-id="910da-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="910da-106">O Skype for Business Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados para transcrições pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="910da-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="910da-107">Você precisa definir quando limpar dados arquivados e exportados.</span><span class="sxs-lookup"><span data-stu-id="910da-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="910da-108">Para obter mais informações sobre como exportar dados usando o cmdlet **Export-CsArchivingData,** consulte Exportar dados arquivados no [Skype for Business Server.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="910da-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="910da-109">Gerenciar a purgação de dados usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="910da-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="910da-110">Para gerenciar a purgação de dados arquivados usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="910da-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="910da-111">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="910da-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="910da-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="910da-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="910da-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="910da-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="910da-114">Clique no nome da configuração global, local ou do pool adequado na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="910da-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="910da-115">Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="910da-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="910da-116">Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="910da-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="910da-117">Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="910da-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="910da-118">Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="910da-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="910da-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="910da-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="910da-120">Gerenciar a purgação de dados usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="910da-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="910da-121">Você pode gerenciar a purgação de dados arquivados usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="910da-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="910da-122">O cmdlet **Set-CsArchivingConfiguration** com o parâmetro EnablePurging permite habilitar ou desabilitar a purgação de dados arquivados.</span><span class="sxs-lookup"><span data-stu-id="910da-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="910da-123">**Invoke-CsArchivingDatabasePurge** permite limpar manualmente os registros do banco de dados de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="910da-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="910da-124">Por exemplo, o comando a seguir habilita a purgação de todos os dados arquivados.</span><span class="sxs-lookup"><span data-stu-id="910da-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="910da-125">Depois que esse comando for executado, o Skype for Business Server limpará todos os registros de arquivamento mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="910da-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="910da-126">O comando a seguir limita a purgação a registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData).**</span><span class="sxs-lookup"><span data-stu-id="910da-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="910da-127">Você também deve definir o parâmetro PurgeExportedArchivesOnly como True ($True):</span><span class="sxs-lookup"><span data-stu-id="910da-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="910da-128">Depois que esse comando for executado, o Skype for Business Server limpará apenas os registros de arquivamento que atenderem a dois critérios: 1) eles são mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays; e, 2) eles foram exportados usando o cmdlet **Export-CsArchivingData.**</span><span class="sxs-lookup"><span data-stu-id="910da-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="910da-129">Para desabilitar a purgação automática de registros de arquivamento, de definir o parâmetro EnablePurging como False ($False):</span><span class="sxs-lookup"><span data-stu-id="910da-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="910da-130">O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros com mais de 24 horas do banco de dados de arquivamento no atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="910da-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="910da-131">Para garantir que todos os registros sejam excluídos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido como False ($False):</span><span class="sxs-lookup"><span data-stu-id="910da-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
