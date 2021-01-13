---
title: Habilitar ou desabilitar o arquivamento no Skype for Business Server
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
description: 'Resumo: Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817591"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Habilitar ou desabilitar o arquivamento no Skype for Business Server

**Resumo:** Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Habilitar ou desabilitar o arquivamento usando o Painel de Controle

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Selecione a configuração global, de site ou de pool apropriada na lista de configurações de arquivo, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:
    
   - Para habilitar o arquivamento apenas para sessões de IM (mensagem instantânea), clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.
    
   - Para desabilitar o arquivamento para a configuração, clique **em Desabilitar arquivamento.**
    
5. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Habilitar ou desabilitar o arquivamento usando o Windows PowerShell

Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration.** Por exemplo, o comando a seguir modifica todas as definições de configuração de arquivamento para que somente as sessões de IM sejam arquivadas. O comando chama o cmdlet **Get-CsArchivingConfiguration** sem nenhum parâmetro para retornar todas as definições de configuração de arquivamento em uso na organização. Esta coleção será então canalada para o cmdlet **Where-Object,** que selecionará apenas as definições nas quais a propriedade EnableArchiving for igual a (-eq) "ImAndWebConf". A coleção filtrada é então canalizada para o cmdlet **Set-CsArchivingConfiguration,** que pega cada item na coleção e altera o valor de EnableArchiving para "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
