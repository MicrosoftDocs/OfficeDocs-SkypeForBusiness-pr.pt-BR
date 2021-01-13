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
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gerenciar a purgação de dados arquivados no Skype for Business Server

**Resumo:** Saiba como gerenciar a purgação de dados arquivados para o Skype for Business Server.
  
O banco de dados de Arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta de e-discovery (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. O Skype for Business Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados para transcrições pesquisáveis. Você precisa definir quando limpar dados arquivados e exportados. 
  
Para obter mais informações sobre como exportar dados usando o cmdlet **Export-CsArchivingData,** consulte Exportar dados arquivados no [Skype for Business Server.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gerenciar a purgação de dados usando o Painel de Controle

Para gerenciar a purgação de dados arquivados usando o Painel de Controle:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração global, local ou do pool adequado na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
   - Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:
    
     - Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.
    
     - Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.
    
   - Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gerenciar a purgação de dados usando o Windows PowerShell

Você pode gerenciar a purgação de dados arquivados usando os seguintes cmdlets do Windows PowerShell:
  
- O cmdlet **Set-CsArchivingConfiguration** com o parâmetro EnablePurging permite habilitar ou desabilitar a purgação de dados arquivados.
    
- **Invoke-CsArchivingDatabasePurge** permite limpar manualmente os registros do banco de dados de Arquivamento.
    
Por exemplo, o comando a seguir habilita a purgação de todos os dados arquivados. Depois que esse comando for executado, o Skype for Business Server limpará todos os registros de arquivamento mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

O comando a seguir limita a purgação a registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData).** Você também deve definir o parâmetro PurgeExportedArchivesOnly como True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Depois que esse comando for executado, o Skype for Business Server limpará apenas os registros de arquivamento que atenderem a dois critérios: 1) eles são mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays; e, 2) eles foram exportados usando o cmdlet **Export-CsArchivingData.**
  
Para desabilitar a purgação automática de registros de arquivamento, de definir o parâmetro EnablePurging como False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros com mais de 24 horas do banco de dados de arquivamento no atl-sql-001.contoso.com. Para garantir que todos os registros sejam excluídos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido como False ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
