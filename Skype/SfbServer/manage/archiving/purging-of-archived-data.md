---
title: Gerenciar a limpeza de dados arquivados no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumo: Saiba como gerenciar a limpeza de dados arquivados do Skype para Business Server.'
ms.openlocfilehash: 5483871d69932239f5d6e654c95edf1feac7b9d9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211029"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gerenciar a limpeza de dados arquivados no Skype para Business Server

**Resumo:** Saiba como gerenciar a limpeza de dados arquivados do Skype para Business Server.
  
O banco de dados de arquivamento não se destina a retenção de longo prazo e Skype para Business Server não ofereça uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto é necessário ser movido para outro armazenamento de dados. Skype para Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar os dados arquivados em transcrições pesquisáveis. Você precisa definir quando limpar dados arquivados e exportados. 
  
Para obter mais informações sobre como exportar dados usando o cmdlet **Export-CsArchivingData** , consulte [exportar os dados arquivados no Skype para Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gerenciar limpeza de dados usando o Painel de Controle

Para gerenciar limpeza de dados usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
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
    
Por exemplo, o seguinte comando habilita a limpeza de todos os dados arquivados. Depois que esse comando for executado, Skype para Business Server excluirá todos os registros de arquivamento mais antigos que o valor especificado para o parâmetro KeepArchivingDataForDays. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

O comando a seguir limita a limpeza aos registros arquivados que foram exportados para um arquivo de dados (usando o cmdlet **Export-CSArchivingData** ). Você também deve definir o parâmetro PurgeExportedArchivesOnly como True ($True):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Depois que esse comando for executado, Skype para Business Server limpará apenas os registros de arquivamento que atenderem a dois critérios: 1) sejam mais antigos que o valor especificado para o parâmetro KeepArchivingDataForDays; e, 2) eles tiverem sido exportados usando o cmdlet **Export-CsArchivingData** .
  
Para desabilitar a limpeza automática dos registros de arquivamento, defina o parâmetro EnablePurging para Falso ($False):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros mais de 24 horas a partir do banco de dados de arquivamento no atl-sql-001.contoso.com. Para assegurar que todos os registros serão limpos, incluindo registros que não foram exportados, o parâmetro PurgeExportedArchivesOnly é definido para Falso ($False):
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
