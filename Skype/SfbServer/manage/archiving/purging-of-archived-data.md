---
title: Gerenciar a eliminação de dados arquivados no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumo: saiba como gerenciar a eliminação de dados arquivados para o Skype for Business Server.'
ms.openlocfilehash: 7953c6085183e3ace0e395f0c8751897acd49380
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818873"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="bd63e-103">Gerenciar a eliminação de dados arquivados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bd63e-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="bd63e-104">**Resumo:** Saiba como gerenciar a eliminação de dados arquivados para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bd63e-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="bd63e-105">O banco de dados de arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento.</span><span class="sxs-lookup"><span data-stu-id="bd63e-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="bd63e-106">O Skype for Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados para transcrições pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="bd63e-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="bd63e-107">Você precisa definir quando limpar dados arquivados e exportados.</span><span class="sxs-lookup"><span data-stu-id="bd63e-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="bd63e-108">Para obter mais informações sobre a exportação de dados usando o cmdlet **Export-CsArchivingData** , consulte [exportar dados arquivados no Skype for Business Server](export-archived-data.md).</span><span class="sxs-lookup"><span data-stu-id="bd63e-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="bd63e-109">Gerenciar limpeza de dados usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="bd63e-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="bd63e-110">Para gerenciar limpeza de dados usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="bd63e-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="bd63e-111">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="bd63e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="bd63e-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bd63e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bd63e-113">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="bd63e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="bd63e-114">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bd63e-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="bd63e-115">Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="bd63e-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="bd63e-116">Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="bd63e-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="bd63e-117">Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="bd63e-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="bd63e-118">Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="bd63e-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="bd63e-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bd63e-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="bd63e-120">Gerenciar limpeza de dados usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd63e-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="bd63e-121">Você pode gerenciar a limpeza de dados arquivados usando os cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bd63e-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="bd63e-122">O cmdlet **Set-CsArchivingConfiguration** com o parâmetro EnablePurging permite que você habilite ou desabilite a limpeza de dados arquivados.</span><span class="sxs-lookup"><span data-stu-id="bd63e-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="bd63e-123">O cmdlet **Invoke-CsArchivingDatabasePurge** permite que você limpe manualmente registros do banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="bd63e-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="bd63e-124">Por exemplo, o seguinte comando habilita a limpeza de todos os dados arquivados.</span><span class="sxs-lookup"><span data-stu-id="bd63e-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="bd63e-125">Depois que esse comando for executado, o Skype for Business Server limpará todos os registros de arquivamento anteriores ao valor especificado para o parâmetro KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="bd63e-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="bd63e-126">O comando a seguir limita a limpeza a registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData** ).</span><span class="sxs-lookup"><span data-stu-id="bd63e-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="bd63e-127">Você também deve definir o parâmetro PurgeExportedArchivesOnly como true ($True):</span><span class="sxs-lookup"><span data-stu-id="bd63e-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="bd63e-128">Depois que esse comando for executado, o Skype for Business Server limpará somente os registros de arquivamento que atenderem a dois critérios: 1) eles são mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays; e 2) eles foram exportados usando o cmdlet **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="bd63e-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="bd63e-129">Para desabilitar a limpeza automática dos registros de arquivamento, defina o parâmetro EnablePurging para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="bd63e-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="bd63e-130">O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros de mais de 24 horas de idade do banco de dados de arquivamento no ATL-SQL-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bd63e-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="bd63e-131">Para assegurar que todos os registros serão limpos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="bd63e-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
