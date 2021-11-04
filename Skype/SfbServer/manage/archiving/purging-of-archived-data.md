---
title: Gerenciar a coleta de dados arquivados no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumo: saiba como gerenciar a coleta de dados arquivados para Skype for Business Server.'
ms.openlocfilehash: e5800711756fcccde90ba9907adbe1e9309a677b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778351"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gerenciar a coleta de dados arquivados no Skype for Business Server

**Resumo:** Saiba como gerenciar a coleta de dados arquivados para Skype for Business Server.
  
O banco de dados de arquivamento não se destina à retenção a longo prazo, e o Skype for Business Server não fornece uma solução de descoberta por e-discovery (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. Skype for Business Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados para transcrições pesquisáveis. Você precisa definir quando limpar dados arquivados e exportados. 
  
Para obter mais informações sobre como exportar dados usando o cmdlet **Export-CsArchivingData,** consulte [Export archived data in Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gerenciar a coleta de dados usando o Painel de Controle

Para gerenciar a purgação de dados arquivados usando o Painel de Controle:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração global, local ou do pool adequado na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
   - Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:
    
     - Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.
    
     - Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.
    
   - Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gerenciar a coleta de dados usando Windows PowerShell

Você pode gerenciar a purgação de dados arquivados usando os seguintes cmdlets Windows PowerShell:
  
- O cmdlet **Set-CsArchivingConfiguration** com o parâmetro EnablePurging permite habilitar ou desabilitar a purgação de dados arquivados.
    
- **Invoke-CsArchivingDatabasePurge** permite limpar manualmente os registros do banco de dados de Arquivamento.
    
Por exemplo, o comando a seguir permite a repuração de todos os dados arquivados. Depois que esse comando for executado, Skype for Business Server limpará todos os registros de arquivamento mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

O comando a seguir limita a purgação para registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData).** Você também deve definir o parâmetro PurgeExportedArchivesOnly como True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Depois que esse comando for executado, Skype for Business Server limpará somente os registros de arquivamento que atendem a dois critérios: 1) eles são mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays; e, 2) eles foram exportados usando o cmdlet **Export-CsArchivingData.**
  
Para desabilitar a purgação automatizada de registros de arquivamento, de definir o parâmetro EnablePurging como False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros com mais de 24 horas do banco de dados de arquivamento no atl-sql-001.contoso.com. Para garantir que todos os registros sejam excluídos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido como False ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
