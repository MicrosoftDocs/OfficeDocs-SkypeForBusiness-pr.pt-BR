---
title: Configurar opções de arquivamento para lidar com falhas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: saiba como bloquear sessões de mensagens instantâneas e de conferência no caso de uma falha do Skype for Business Server que impediria o arquivamento.'
ms.openlocfilehash: 38f79277ff12aa8e716b034e8393a4d8b71cdbba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286236"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opções de arquivamento para lidar com falhas no Skype for Business Server

**Resumo:** Saiba como bloquear mensagens de chat e de conferência no caso de uma falha do Skype for Business Server que impede o arquivamento.
  
Se o arquivamento for um requisito para sua organização, você poderá bloquear as sessões de chat e de conferência no caso de uma falha do Skype for Business Server que impediria o arquivamento. Isso às vezes é chamado de modo crítico. Por exemplo, se houver um problema com um serviço de armazenamento, o IM seria bloqueado para usuários cujas comunicações estivessem habilitadas para arquivamento. Tanto sessões de IM quanto de conferência são restauradas após a correção das falhas. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar modo crítico usando o Painel de Controle

Para especificar se sessões de comunicação devem ser permitidas caso uma falha impossibilite o arquivamento:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar** e depois clique em **Mostrar detalhes**.
    
5. Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de webconferência e mensagens instantâneas (IM) se o arquivamento falhar**.
    
6. Clique em **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar modo crítico usando o Windows PowerShell

Você também pode especificar se as sessões de comunicação devem ser permitidas em caso de falha que impedem o arquivamento usando o cmdlet **set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.
  
Por exemplo, o comando a seguir desabilita as comunicações no caso de uma falha de arquivamento:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

O seguinte comando habilita as comunicações em caso de falha no arquivamento:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

