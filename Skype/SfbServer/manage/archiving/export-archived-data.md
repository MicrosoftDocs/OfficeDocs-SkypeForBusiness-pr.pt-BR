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
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>Exportar dados arquivados no Skype for Business Server 2015

**Resumo:** Saiba como exportar os dados arquivados para Skype para Business Server 2015.
  
Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML).
  
Se você habilitar a integração do Microsoft Exchange, os dados sejam arquivados em repositórios do Exchange. Dados arquivados no Exchange são pesquisáveis e detectáveis. Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportando dados de arquivamento usando Cmdlets do Windows PowerShell

Você pode exportar dados arquivados usando o cmdlet Export-CSArchivingData. 
  
O seguinte comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1 de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

O comando a seguir exporta dados para um único usuário de arquivamento: kenmyer@contoso.com. Isso é feito incluindo o parâmetro de UserUri, seguido pelo endereço SIP do usuário. Por exemplo: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

