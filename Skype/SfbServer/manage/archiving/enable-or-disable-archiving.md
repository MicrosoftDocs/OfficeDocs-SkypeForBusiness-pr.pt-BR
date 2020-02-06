---
title: Habilitar ou desabilitar o arquivamento no Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: 8c970dba9a76abdb0c9417a5da5c7aa642fa059c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818913"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar ou desabilitar o arquivamento no Skype for Business Server

**Resumo:** Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar ou desabilitar o arquivamento usando o Painel de Controle

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Selecione a configuração global, local ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:
    
   - Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.
    
   - Para desabilitar o arquivamento da configuração, clique em **Desabilitar arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar ou desabilitar arquivamento usando o Windows PowerShell

Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration**. Por exemplo: o comando a seguir modifica todas as configurações de arquivamento, de forma que somente as sessões de IM sejam arquivadas. O comando acessa o cmdlet **Get-CsArchivingConfiguration** sem nenhum parâmetro para devolver todas as configurações de arquivamento usadas atualmente na organização. Essa coleção é então enviada para o cmdlet **Where-Object**, que seleciona somente as configurações nas quais a propriedade EnableArchiving é igual a (-eq) "ImAndWebConf". A coleção filtrada é então encaminhada para o cmdlet **Set-CsArchivingConfiguration**, que pega cada um dos itens da coleção e altera o valor de EnableArchiving para "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
