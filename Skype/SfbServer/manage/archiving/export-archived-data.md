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
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportar dados arquivados no Skype for Business Server

**Resumo:** Saiba como exportar dados arquivados para o Skype for Business Server.
  
Os dados arquivados em bancos de dados de Arquivamento não podem ser pesquisados ou em um formato aceitável, mas você pode usar o cmdlet **Export-CsArchivingData** para extrair registros do banco de dados e salvá-los como um arquivo de Email Eletrônico do Outlook (EML).
  
Se você habilitar a integração com o Microsoft Exchange, os dados serão arquivados nos armazenamentos do Exchange. Os dados arquivados no Exchange são pesquisáveis e descobertos. Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportando dados de arquivamento usando cmdlets do Windows PowerShell

Você pode exportar dados arquivados usando o Export-CSArchivingData cmdlet. 
  
O comando a seguir exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.contoso.com desde 1º de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@contoso.com. Isso é feito incluindo-se o parâmetro UserUri seguido pelo endereço SIP do usuário. Por exemplo: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData.](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)
  

