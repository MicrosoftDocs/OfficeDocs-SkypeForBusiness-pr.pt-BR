---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para o  Servidor de Mediação, você pode especificar:'
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215142"
---
# <a name="mediation-service-settings-expander"></a>Expansor de Configurações de Serviço de Mediação

Para o  **Servidor de Mediação**, você pode especificar:

Se você estiver posicionando o servidor de mediação no pool de front-ends ou no servidor Standard Edition, marque a caixa de seleção **servidor de mediação colocado habilitado**. Se você escolher não posicionar o Servidor de Mediação, não haverá configurações para definição nesta seção.

Se você tiver habilitado o posicionamento do Servidor de Mediação, será necessário definir o intervalo de porta de escuta no servidor para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

Defina os gateways PSTN associados ao Servidor de Mediação posicionado. Se você já tiver definido os gateways, eles estarão disponíveis para associação com o Servidor de Mediação.

Se houver mais de um gateway associado ao Servidor de Mediação, o primeiro gateway associado será o gateway padrão. Se você precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir e configurar as definições para o pool de front-ends Enterprise Edition ou servidor Standard Edition, consulte [definindo e configurando a topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implantando servidores de mediação e definindo pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


