---
title: Exportar dados arquivados no Skype for Business Server
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
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Resumo: saiba como exportar dados arquivados para o Skype for Business Server.'
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817561"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="3a828-103">Exportar dados arquivados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3a828-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="3a828-104">**Resumo:** Saiba como exportar dados arquivados para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a828-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="3a828-105">Os dados arquivados em bancos de dados de Arquivamento não podem ser pesquisados ou em um formato aceitável, mas você pode usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo de Email Eletrônico do Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="3a828-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="3a828-106">Se você habilitar a integração com o Microsoft Exchange, os dados serão arquivados nos armazenamentos do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a828-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="3a828-107">Os dados arquivados no Exchange são pesquisáveis e descobertos.</span><span class="sxs-lookup"><span data-stu-id="3a828-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="3a828-108">Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a828-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3a828-109">Exportando dados de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a828-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3a828-110">Você pode exportar dados arquivados usando o Export-CSArchivingData cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a828-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="3a828-111">O comando a seguir exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1º de junho de 2012.</span><span class="sxs-lookup"><span data-stu-id="3a828-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="3a828-112">O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="3a828-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="3a828-113">O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3a828-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="3a828-114">Isso é feito incluindo-se o parâmetro UserUri seguido pelo endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="3a828-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="3a828-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a828-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="3a828-116">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData.](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3a828-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

