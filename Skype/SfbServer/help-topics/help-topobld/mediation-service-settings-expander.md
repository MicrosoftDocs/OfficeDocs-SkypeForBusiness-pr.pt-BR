---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'No caso do Servidor de Mediação, você pode especificar o seguinte:'
ms.openlocfilehash: fcff87faeb5911d12806f80499c2b2f0d63caff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285600"
---
# <a name="mediation-service-settings-expander"></a>Expansor de Configurações de Serviço de Mediação

No caso do **Servidor de Mediação**, você pode especificar o seguinte:

Se você estiver posicionando o servidor de mediação no pool de front-ends ou o servidor Standard Edition, marque a caixa de seleção **servidor de mediação posicionado habilitado**. Se você optar por não colocar o servidor de mediação, não haverá configurações definíveis nesta seção.

Se você tiver habilitado a colocação do servidor de mediação, será necessário definir o intervalo de portas de escuta no servidor para a segurança da camada de transporte (TLS). Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

Você define os gateways PSTN associados ao servidor de mediação posicionado. Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação.

Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão. Se precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir e definir as configurações do pool de front-end do Enterprise Edition ou do servidor Standard Edition, consulte [definindo e configurando a topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e implantando [servidores de mediação e definindo pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


