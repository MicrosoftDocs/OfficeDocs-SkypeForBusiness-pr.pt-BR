---
title: Configurar opções de arquivamento para lidar com falhas no Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: Saiba como bloquear sessões de IM e conferência no caso de uma falha do Skype for Business Server que impeça o arquivamento.'
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817671"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opções de arquivamento para lidar com falhas no Skype for Business Server

**Resumo:** Saiba como bloquear IM e sessões de conferência no caso de uma falha do Skype for Business Server que impeça o arquivamento.
  
Se o arquivamento for um requisito para sua organização, você poderá bloquear sessões de IM e conferência em caso de falha do Skype for Business Server que impeça o arquivamento. Isso algumas vezes é chamado de modo crítico. Por exemplo, se houver um problema com um serviço de armazenamento, as IMs serão bloqueadas para usuários cujas comunicações estão habilitadas para arquivamento. As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar o modo crítico usando o Painel de Controle

Para especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração global, de site ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar** e em **Mostrar detalhes.**
    
5. Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de conferência da Web e mensagens instantâneas (IM) se o arquivamento falhar**.
    
6. Clique em **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar o modo crítico usando o Windows PowerShell

Também é possível especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento usando o cmdlet **Set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.
  
Por exemplo, o seguinte comando desabilita as comunicações no caso de uma falha de arquivamento:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

O próximo comando habilita as comunicações no caso de uma falha de arquivamento:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obter mais informações, consulte o tópico de Ajuda para o cmdlet [Set-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
  

