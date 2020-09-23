---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:'
ms.openlocfilehash: 94cf0f611d754dc614111add734bf231c92c5a81
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217002"
---
# <a name="add-trusted-application-pool-fqdn"></a>Adicionar Pool de Aplicativo Confiável
 
Para definir um FQDN (nome de domínio totalmente qualificado) do pool de Aplicativos Confiáveis, especifique o seguinte:
  
Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.
  
Selecione  **Pool de múltiplos computadores ** caso esteja implementando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **Pool de computador único ** caso não necessite de balanceamento de carga ou alta disponibilidade.
  
> [!IMPORTANT]
> Um único Servidor de Aplicativos Confiáveis não pode ser convertido para um pool de servidores posteriormente. Caso ache que precisará de um pool no futuro, agora você pode implantar um pool de múltiplos servidores contendo um único computador e adicionando servidores quando necessário. 
  
Para maiores detalhes sobre pools de Aplicativos Confiáveis, consulte  [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

