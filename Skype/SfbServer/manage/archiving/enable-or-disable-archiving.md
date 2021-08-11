---
title: Habilitar ou desabilitar o arquivamento Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: saiba como habilitar ou desabilitar o arquivamento Skype for Business Server.'
ms.openlocfilehash: 83ed391ed482d3bd744e963e1589726729a52b6e3f1c65a776b213a809eabed4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283373"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar ou desabilitar o arquivamento Skype for Business Server

**Resumo:** Saiba como habilitar ou desabilitar o arquivamento Skype for Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar ou desabilitar o arquivamento usando o Painel de Controle

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Selecione a configuração global, de site ou de pool apropriada na lista de configurações de arquivo, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:
    
   - Para habilitar o arquivamento apenas para sessões de IM (mensagem instantânea), clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.
    
   - Para desabilitar o arquivamento da configuração, clique em **Desabilitar arquivamento**.
    
5. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar ou desabilitar o arquivamento usando Windows PowerShell

Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration.** Por exemplo, o comando a seguir modifica todas as configurações de arquivamento para que apenas as sessões de IM sejam arquivadas. O comando chama o cmdlet **Get-CsArchivingConfiguration** sem parâmetros para retornar todas as configurações de arquivamento em uso na organização. Essa coleção é então canalada para o cmdlet **Where-Object,** que seleciona apenas as configurações em que a propriedade EnableArchiving é igual a (-eq) "ImAndWebConf". A coleção filtrada é então canalizada para o cmdlet **Set-CsArchivingConfiguration,** que leva cada item da coleção e altera o valor de EnableArchiving para "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
