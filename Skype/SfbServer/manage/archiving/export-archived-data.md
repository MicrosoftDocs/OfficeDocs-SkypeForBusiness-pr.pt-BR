---
title: Exportar dados arquivados no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumo: Saiba como exportar os dados arquivados para Skype para Business Server 2015.'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="09e3e-103">Exportar dados arquivados no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09e3e-103">Export archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="09e3e-104">**Resumo:** Saiba como exportar os dados arquivados para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="09e3e-104">**Summary:** Learn how to export archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="09e3e-105">Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML).</span><span class="sxs-lookup"><span data-stu-id="09e3e-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="09e3e-106">Se você habilitar a integração do Microsoft Exchange, os dados sejam arquivados em repositórios do Exchange.</span><span class="sxs-lookup"><span data-stu-id="09e3e-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="09e3e-107">Dados arquivados no Exchange são pesquisáveis e detectáveis.</span><span class="sxs-lookup"><span data-stu-id="09e3e-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="09e3e-108">Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.</span><span class="sxs-lookup"><span data-stu-id="09e3e-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="09e3e-109">Exportando dados de arquivamento usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09e3e-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="09e3e-110">Você pode exportar dados arquivados usando o cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="09e3e-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="09e3e-p102">O seguinte comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1 de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="09e3e-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="09e3e-113">O comando a seguir exporta dados para um único usuário de arquivamento: kenmyer@contoso.com. Isso é feito incluindo o parâmetro de UserUri, seguido pelo endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="09e3e-113">The following command exports archiving data for a single user: kenmyer@contoso.com. This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="09e3e-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="09e3e-114">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="09e3e-115">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="09e3e-115">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

