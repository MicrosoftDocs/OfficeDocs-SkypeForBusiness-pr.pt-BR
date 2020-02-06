---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Para definir um FQDN (nome de domínio totalmente qualificado) do pool de aplicativos confiáveis, especifique o seguinte:'
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787731"
---
# <a name="add-trusted-application-pool-fqdn"></a>Adicionar Pool de Aplicativo Confiável
 
Para definir um FQDN (nome de domínio totalmente qualificado) do pool de aplicativos confiáveis, especifique o seguinte:
  
Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.
  
Selecione **vários pools de computadores** se você estiver implantando um pool de servidores para os aplicativos confiáveis de balanceamento de carga e alta disponibilidade, ou selecione **um pool de computador único** se você não precisar de balanceamento de carga ou de alta disponibilidade.
  
> [!IMPORTANT]
> Um único servidor de aplicativos confiáveis não pode ser convertido em um pool de servidores mais tarde. Se você acha que pode precisar de um pool no futuro, poderá implantar um pool de vários servidores com um único computador agora e adicionar servidores quando necessário. 
  
Para obter detalhes sobre pools de aplicativos confiáveis, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

