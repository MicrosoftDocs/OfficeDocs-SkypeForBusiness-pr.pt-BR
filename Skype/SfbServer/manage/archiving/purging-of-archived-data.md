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
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gerenciar a eliminação de dados arquivados no Skype for Business Server

**Resumo:** Saiba como gerenciar a eliminação de dados arquivados para o Skype for Business Server.
  
O banco de dados de arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. O Skype for Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados para transcrições pesquisáveis. Você precisa definir quando limpar dados arquivados e exportados. 
  
Para obter mais informações sobre a exportação de dados usando o cmdlet **Export-CsArchivingData** , consulte [exportar dados arquivados no Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gerenciar limpeza de dados usando o Painel de Controle

Para gerenciar limpeza de dados usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:
    
   - Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:
    
     - Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.
    
     - Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.
    
   - Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gerenciar limpeza de dados usando o Windows PowerShell

Você pode gerenciar a limpeza de dados arquivados usando os cmdlets do Windows PowerShell:
  
- O cmdlet **Set-CsArchivingConfiguration** com o parâmetro EnablePurging permite que você habilite ou desabilite a limpeza de dados arquivados.
    
- O cmdlet **Invoke-CsArchivingDatabasePurge** permite que você limpe manualmente registros do banco de dados de arquivamento.
    
Por exemplo, o seguinte comando habilita a limpeza de todos os dados arquivados. Depois que esse comando for executado, o Skype for Business Server limpará todos os registros de arquivamento anteriores ao valor especificado para o parâmetro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

O comando a seguir limita a limpeza a registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData** ). Você também deve definir o parâmetro PurgeExportedArchivesOnly como true ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Depois que esse comando for executado, o Skype for Business Server limpará somente os registros de arquivamento que atenderem a dois critérios: 1) eles são mais antigos do que o valor especificado para o parâmetro KeepArchivingDataForDays; e 2) eles foram exportados usando o cmdlet **Export-CsArchivingData** .
  
Para desabilitar a limpeza automática dos registros de arquivamento, defina o parâmetro EnablePurging para Falso ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros de mais de 24 horas de idade do banco de dados de arquivamento no ATL-SQL-001.contoso.com. Para assegurar que todos os registros serão limpos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido para Falso ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
