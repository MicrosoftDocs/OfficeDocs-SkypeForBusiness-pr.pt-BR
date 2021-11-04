---
title: Configurar opções de arquivamento para lidar com falhas em Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: saiba como bloquear sessões de IM e conferência no caso de uma falha Skype for Business Server que impediria o arquivamento.'
ms.openlocfilehash: 24bfa5190f4aa86a51d7737c952e6536a7d89b34
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767919"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opções de arquivamento para lidar com falhas em Skype for Business Server

**Resumo:** Saiba como bloquear sessões de IM e conferência no caso de uma falha Skype for Business Server que impediria o arquivamento.
  
Se o arquivamento for um requisito para sua organização, você poderá bloquear sessões de IM e conferência no caso de uma falha Skype for Business Server que impediria o arquivamento. Às vezes, isso é chamado de modo crítico. Por exemplo, se houver um problema com um serviço de armazenamento, o IM seria bloqueado para usuários cujas comunicações estão habilitadas para arquivamento. As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar o modo crítico usando o Painel de Controle

Para especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração global, site ou pool apropriada na lista de configurações de arquivamento, clique em **Editar** e em **Mostrar detalhes.**
    
5. Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de conferência da Web e mensagens instantâneas (IM) se o arquivamento falhar**.
    
6. Clique em **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar o modo crítico usando Windows PowerShell

Você também pode especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento usando o cmdlet **Set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.
  
Por exemplo, o comando a seguir desabilita as comunicações no caso de uma falha de arquivamento:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

O próximo comando habilita as comunicações no caso de uma falha de arquivamento:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obter mais informações, consulte o tópico Ajuda para o cmdlet [Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
