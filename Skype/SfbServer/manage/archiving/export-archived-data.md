---
title: Exportar dados arquivados no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumo: Saiba como exportar os dados arquivados para Skype para Business Server.'
ms.openlocfilehash: fd17fda9d36c5739d9d1cab7845921a442a4155d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884955"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="fe6ab-103">Exportar dados arquivados no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="fe6ab-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="fe6ab-104">**Resumo:** Saiba como exportar os dados arquivados para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="fe6ab-105">Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML).</span><span class="sxs-lookup"><span data-stu-id="fe6ab-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="fe6ab-106">Se você habilitar a integração do Microsoft Exchange, os dados sejam arquivados em repositórios do Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="fe6ab-107">Dados arquivados no Exchange são pesquisáveis e detectáveis.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="fe6ab-108">Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fe6ab-109">Exportando dados de arquivamento usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe6ab-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fe6ab-110">Você pode exportar dados arquivados usando o cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="fe6ab-p102">O seguinte comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1 de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="fe6ab-113">O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="fe6ab-114">Isso é feito incluindo o parâmetro de UserUri, seguido pelo endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="fe6ab-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="fe6ab-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fe6ab-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="fe6ab-116">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fe6ab-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

