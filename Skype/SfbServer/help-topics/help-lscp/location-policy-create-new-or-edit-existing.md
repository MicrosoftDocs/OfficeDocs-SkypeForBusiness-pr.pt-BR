---
title: Política de localização criar nova ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: É possível configurar as políticas de local para determinar se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 2623e5f3a723dc0ce061109e047961d68bd7badd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686384"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Política de Local: Criar Nova ou Editar Existente

É possível configurar as políticas de local para determinar se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de localização que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de local exige um nome. As políticas de local global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de local do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de local, o nome não pode ser alterado.

- **Habilite o 9-1-1 avançado (E9-1-1)** Marque esta caixa de seleção para habilitar o E9-1-1 para os usuários atribuídos a essa política de localização.

- **Local** Especifique se os usuários são solicitados a fornecer informações de localização:

  - **Obrigatório** Selecione essa opção se os usuários devem ser solicitados a fornecer informações de localização quando o cliente estiver registrado em um novo local. Os usuários podem ignorar essa solicitação sem inserir informações de local.

  - **Não é necessário** Selecione essa opção se os usuários não devem ser solicitados a fornecer informações de localização.

  - **Aviso** Selecione essa opção se os usuários devem ser solicitados a fornecer informações de localização, mas verão uma mensagem de isenção de responsabilidade se recusarem o prompt sem inserir as informações. Os usuários poderão apenas completar uma chamada de emergência até inserirem as informações de local.

- **Usar o local somente para E9-1-1** Marque esta caixa de seleção se as informações de localização forem usadas apenas para chamadas de emergência.

- **Uso de PSTN** Selecione o uso de rede telefônica pública comutada (PSTN) que será usado para determinar qual rota de voz será usada para direcionar as chamadas de emergência dos clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo. As opções são **Interna**, **Local** ou **Chamada interurbana**.

- **E9-1-1 número de discagem** Especifique o número discado para acessar serviços de emergência.

- **Máscara de discagem E9-1-1** Especifique um número que um usuário discará, que será traduzido para o número de discagem de emergência. Por exemplo, insira um valor de 212 nesse campo de modo que um usuário possa discar 212 a fim de entrar em contato com os serviços de emergência. Isso permite que números de emergência alternativos sejam discados e ainda que a chamada atinja serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar o número do país ou da região, em vez do número da país ou região em que estão no momento). É possível definir várias máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O tamanho máximo da cadeia de caracteres é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.

    > [!IMPORTANT]
    > Certifique-se de que a máscara de discagem não seja a mesma que o número em um intervalo de números de estacionamento de chamada, pois o roteamento de estacionamento de chamada tem precedência sobre a conversão da cadeia de caracteres de discagem de emergência. Para ver os intervalos numéricos do parque da chamada, clique em **recursos de voz** na barra de navegação à esquerda e, em seguida, clique em **ligar para estacionamento**.

- **URI de notificação** Especifique um ou mais URIs SIP a serem notificados quando uma chamada de emergência for feita. Por exemplo, digite o URI de SIP do escritório de segurança da empresa a fim de notificar a equipe de segurança com uma mensagem instantânea sempre que uma chamada de emergência for feita. Se o local do chamador estiver disponível, o local será incluído na notificação. É possível especificar vários URIs SIP como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". A cadeia de cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Também é possível especificar listas de distribuição.

- **URL de conferência** Especifique o URI SIP (número de telefone, nesse caso) para que terceiros seja conferência em chamadas de emergência. Por exemplo, digite o número de telefone do escritório de segurança da empresa de modo que ele receba uma chamada quando uma chamada de emergência é feita. A configuração para  **Modo de conferência** determina se o terceiro pode participar ou apenas escutar a chamada. A cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:.

- **Modo de conferência** Se você especificou um valor para o **URI da conferência**, defina esse campo como um dos seguintes valores:

  - **Unilateral** Especifica que a terceira parte só pode escutar na chamada entre o chamador e o operador PSAP.

  - **Bidirecional** Especifica que a terceira parte pode participar da chamada entre o chamador e o operador PSAP.

Para obter detalhes sobre os recursos e recursos do serviço de emergência do Enterprise Voice, consulte [visão geral do E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.


