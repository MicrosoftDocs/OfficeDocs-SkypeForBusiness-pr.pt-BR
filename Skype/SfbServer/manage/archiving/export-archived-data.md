---
title: Exportar dados arquivados em Skype for Business Server
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
description: 'Resumo: saiba como exportar dados arquivados para Skype for Business Server.'
ms.openlocfilehash: bb23861ea7615584de3ce6247f7281d94b5c60853767aaaa6ae495d3a6264dc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311079"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar dados arquivados em Skype for Business Server

**Resumo:** Saiba como exportar dados arquivados para Skype for Business Server.
  
Os dados arquivados em bancos de dados de arquivamento não são pesquisáveis ou em um formato acessível, mas você pode usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo Outlook Email Eletrônico (EML).
  
Se você habilitar a integração Exchange Microsoft, os dados serão arquivados Exchange armazenamentos. Os dados arquivados no Exchange são pesquisáveis e descobertos. Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportando dados de arquivamento usando Windows PowerShell cmdlets

Você pode exportar dados arquivados usando o cmdlet Export-CSArchivingData. 
  
O comando a seguir exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1º de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@contoso.com. Isso é feito incluindo o parâmetro UserUri seguido pelo endereço SIP do usuário. Por exemplo: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
