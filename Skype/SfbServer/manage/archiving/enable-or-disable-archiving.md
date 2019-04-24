---
title: Habilitar ou desabilitar o arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: Saiba como habilitar ou desabilitar o arquivamento no Skype para Business Server.'
ms.openlocfilehash: b7f9ab424a9fc24c733fa61c75c1d4564b636941
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250907"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar ou desabilitar o arquivamento no Skype para Business Server

**Resumo:** Aprenda a habilitar ou desabilitar o arquivamento no Skype para Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar ou desabilitar o arquivamento usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Selecione a configuração global, local ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:
    
   - Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.
    
   - Para desabilitar o arquivamento da configuração, clique em **Desabilitar arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar ou desabilitar arquivamento usando o Windows PowerShell

Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration**. Por exemplo: o comando a seguir modifica todas as configurações de arquivamento, de forma que somente as sessões de IM sejam arquivadas. O comando acessa o cmdlet **Get-CsArchivingConfiguration** sem nenhum parâmetro para devolver todas as configurações de arquivamento usadas atualmente na organização. Essa coleção é então enviada para o cmdlet **Where-Object**, que seleciona somente as configurações nas quais a propriedade EnableArchiving é igual a (-eq) "ImAndWebConf". A coleção filtrada é então encaminhada para o cmdlet **Set-CsArchivingConfiguration**, que pega cada um dos itens da coleção e altera o valor de EnableArchiving para "ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
