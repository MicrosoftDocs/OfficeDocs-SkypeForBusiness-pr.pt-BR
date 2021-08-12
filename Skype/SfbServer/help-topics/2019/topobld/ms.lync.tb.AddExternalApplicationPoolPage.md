---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:'
ms.openlocfilehash: fa52ba0281b87c5e522403e8b88d50399128f041f52cc680c8718207b9b7f870
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302895"
---
# <a name="add-trusted-application-pool-fqdn"></a>Adicionar Pool de Aplicativo Confiável
 
Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:
  
Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.
  
Selecione  **Pool de múltiplos computadores** caso esteja implementando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **Pool de computador único** caso não necessite de balanceamento de carga ou alta disponibilidade.
  
> [!IMPORTANT]
> Um único Servidor de Aplicativos Confiáveis não pode ser convertido para um pool de servidores posteriormente. Caso ache que precisará de um pool no futuro, agora você pode implantar um pool de múltiplos servidores contendo um único computador e adicionando servidores quando necessário. 
  
Para maiores detalhes sobre pools de Aplicativos Confiáveis, consulte  [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
