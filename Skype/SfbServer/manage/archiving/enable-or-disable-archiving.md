---
title: Habilitar ou desabilitar o arquivamento Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: saiba como habilitar ou desabilitar o arquivamento Skype for Business Server.'
ms.openlocfilehash: ad59cd2f8bf22ae0f4ac8b8ba08c84b40fbeffb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747327"
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
