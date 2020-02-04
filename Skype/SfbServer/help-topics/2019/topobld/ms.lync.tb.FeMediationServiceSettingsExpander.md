---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'No caso do Servidor de Mediação, você pode especificar o seguinte:'
ms.openlocfilehash: badc56265dfab1e8c1a46f7a3d9f122ec845d162
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702176"
---
# <a name="mediation-service-settings-expander"></a>Expansor de Configurações de Serviço de Mediação

No caso do **Servidor de Mediação**, você pode especificar o seguinte:

Se você estiver posicionando o servidor de mediação no pool de front-ends ou o servidor Standard Edition, marque a caixa de seleção **servidor de mediação posicionado habilitado**. Se você optar por não colocar o servidor de mediação, não haverá configurações definíveis nesta seção.

Se você tiver habilitado a colocação do servidor de mediação, será necessário definir o intervalo de portas de escuta no servidor para a segurança da camada de transporte (TLS). Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

Você define os gateways PSTN associados ao servidor de mediação posicionado. Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação.

Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão. Se precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir e definir as configurações do pool de front-end do Enterprise Edition ou do servidor Standard Edition, consulte [definindo e configurando a topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implantando servidores de mediação e definindo pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


