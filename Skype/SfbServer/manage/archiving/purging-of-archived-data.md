---
title: Gerenciar a limpeza de dados arquivados no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Resumo: Saiba como gerenciar a limpeza de dados arquivados do Skype para Business Server 2015.'
ms.openlocfilehash: caeddcd927c20f0622cbd45b6d93abb2bf5d6618
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server-2015"></a>Gerenciar a limpeza de dados arquivados no Skype for Business Server 2015

**Resumo:** Saiba como gerenciar a limpeza de dados arquivados do Skype para Business Server 2015.
  
O banco de dados de arquivamento não se destina a retenção de longo prazo e Skype para Business Server 2015 não ofereça uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto é necessário ser movido para outro armazenamento de dados. Skype para Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar os dados arquivados em transcrições pesquisáveis. Você precisa definir quando limpar dados arquivados e exportados. 
  
Para obter mais informações sobre como exportar dados usando o cmdlet **Export-CsArchivingData** , consulte [exportar os dados arquivados no Skype para Business Server 2015](export-archived-data.md).
  
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

O exemplo a seguir usa o cmdlet **Invoke-CsArchivingDatabasePurge** para limpar todos os registros mais de 24 horas a partir do banco de dados de arquivamento no atl-sql-001.contoso.com. Para garantir que todos os registros são excluídos, incluindo os registros que não tenham sido exportados, o parâmetro PurgeExportedArchivesOnly é definido como False ($False):
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```