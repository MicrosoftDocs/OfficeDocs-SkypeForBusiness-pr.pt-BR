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
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar dados arquivados no Skype para Business Server

**Resumo:** Saiba como exportar os dados arquivados para Skype para Business Server.
  
Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML).
  
Se você habilitar a integração do Microsoft Exchange, os dados sejam arquivados em repositórios do Exchange. Dados arquivados no Exchange são pesquisáveis e detectáveis. Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportando dados de arquivamento usando Cmdlets do Windows PowerShell

Você pode exportar dados arquivados usando o cmdlet Export-CSArchivingData. 
  
O seguinte comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1 de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@contoso.com. Isso é feito incluindo o parâmetro de UserUri, seguido pelo endereço SIP do usuário. Por exemplo: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

