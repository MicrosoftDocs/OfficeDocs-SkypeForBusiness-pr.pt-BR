---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:'
ms.openlocfilehash: f0420271b2ae0b2cea5134ca9ea2ace7014168b9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389523"
---
# <a name="add-trusted-application-pool-fqdn"></a>Adicionar Pool de Aplicativo Confiável
 
Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:
  
Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.
  
Selecione  **Pool de múltiplos computadores** caso esteja implementando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **Pool de computador único** caso não necessite de balanceamento de carga ou alta disponibilidade.
  
> [!IMPORTANT]
> Um único Servidor de Aplicativos Confiáveis não pode ser convertido para um pool de servidores posteriormente. Caso ache que precisará de um pool no futuro, agora você pode implantar um pool de múltiplos servidores contendo um único computador e adicionando servidores quando necessário. 
  
Para maiores detalhes sobre pools de Aplicativos Confiáveis, consulte  [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
