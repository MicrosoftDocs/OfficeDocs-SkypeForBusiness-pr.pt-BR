---
title: Configurar opções de arquivamento para lidar com falhas no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: Saiba como bloquear sessões de mensagens Instantâneas e conferência no caso de um Skype para falha do servidor de negócios que impediriam a arquivamento.'
ms.openlocfilehash: 952ee82ca3be045fc0407a6ce2f61fdaead12030
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998711"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurar opções de arquivamento para lidar com falhas no Skype para Business Server

**Resumo:** Saiba como bloquear sessões de mensagens Instantâneas e conferência no caso de um Skype para falha do servidor de negócios que impediriam a arquivamento.
  
Se o arquivamento é um requisito para sua organização, você pode bloquear sessões de mensagens Instantâneas e conferência em caso de um Skype para falha do servidor de negócios que impediria a arquivamento. Isso às vezes é chamado de modo crítico. Por exemplo, se houver um problema com um serviço de armazenamento, o IM seria bloqueado para usuários cujas comunicações estivessem habilitadas para arquivamento. Tanto sessões de IM quanto de conferência são restauradas após a correção das falhas. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurar modo crítico usando o Painel de Controle

Para especificar se sessões de comunicação devem ser permitidas caso uma falha impossibilite o arquivamento:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar** e depois clique em **Mostrar detalhes**.
    
5. Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de webconferência e mensagens instantâneas (IM) se o arquivamento falhar**.
    
6. Clique em **Confirmar**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurar modo crítico usando o Windows PowerShell

Você também pode especificar se as sessões de comunicação devem ter permissão no caso de uma falha que impediria o arquivamento usando o cmdlet **Set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.
  
Por exemplo, o comando a seguir desabilita communications no caso de uma falha de arquivamento:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

O seguinte comando habilita as comunicações em caso de falha no arquivamento:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

