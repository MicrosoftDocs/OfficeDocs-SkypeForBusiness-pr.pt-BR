---
title: Política de Local Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: É possível configurar políticas de local para determinar se o 9-1-1 (E9-1-1) Enhanced está habilitado e como ele é usado, bem como como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: f171d841ec68b3e0b0b4f7c8b9d374ff2261d149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803961"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Política de Local: Criar Nova ou Editar Existente

É possível configurar políticas de local para determinar se o 9-1-1 (E9-1-1) Enhanced está habilitado e como ele é usado, bem como como as informações de local são usadas para usuários e contatos.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de local que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de local exige um nome. As políticas de local global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de local do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de local, o nome não pode ser alterado.

- **Habilitar 9-1-1 Enhanced (E9-1-1)** Marque essa caixa de seleção para habilitar o E9-1-1 para usuários aos quais essa política de local foi atribuída.

- **Localização** Especifique se os usuários serão solicitados a obter informações de local:

  - **Obrigatório** Selecione essa opção se os usuários devem ser solicitados a solicitar informações de local quando seus clientes se registram em um novo local. Os usuários podem ignorar essa solicitação sem inserir informações de local.

  - **Não obrigatório** Selecione essa opção se os usuários não devem ser solicitados a solicitar informações de localização.

  - **Aviso de isenção de responsabilidade** Selecione essa opção se os usuários devem ser solicitados a inserir informações de local, mas verão uma mensagem de aviso de isenção de responsabilidade se recusarem a solicitação sem inserir as informações. Os usuários poderão apenas completar uma chamada de emergência até inserirem as informações de local.

- **Use location for E9-1-1 only** Marque essa caixa de seleção se as informações de local devem ser usadas somente para chamadas de emergência.

- **Uso de PSTN** Selecione o uso da PSTN (Rede Telefônica Pública Comutado) que será usada para determinar qual rota de voz será usada para rotear chamadas de emergência de clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo. As opções são **Interna**, **Local** ou **Longa distância**.

- **Número de discagem de E9-1-1** Especifique o número discado para alcançar os serviços de emergência.

- **Máscara de discagem E9-1-1** Especifique um número que um usuário disca, que é convertido no número de discagem de emergência. Por exemplo, insira um valor de 212 nesse campo de modo que um usuário possa discar 212 a fim de entrar em contato com os serviços de emergência. Isso permite que números de emergência alternativos sejam discados e ainda assim a chamada chegue aos serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar o número desse país ou região em vez do número do país ou região em que está no momento). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O tamanho máximo da string é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.

    > [!IMPORTANT]
    > Certifique-se de que a máscara de discagem não seja a mesma que o número em um intervalo de números de estacionamento de chamada, pois o roteamento de estacionamento de chamada tem precedência sobre a conversão de string de discagem de emergência. Para ver os intervalos de números do Estacionamento de Chamadas, clique em **Recursos** de Voz na barra de navegação esquerda e clique em **Estacionamento de Chamadas.**

- **URI de notificação** Especifique um ou mais URIs SIP a serem notificados quando uma chamada de emergência for feita. Por exemplo, digite o URI SIP do escritório de segurança da empresa a fim de notificar a equipe de segurança com uma mensagem instantânea sempre que uma chamada de emergência for feita. Se o local do chamador estiver disponível, o local será incluído na notificação. É possível especificar múltiplos URIs SIP como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Também é possível especificar listas de distribuição.

- **URI de conferência** Especifique o URI do SIP (número de telefone, neste caso) para que um terceiro seja colocado em conferência em chamadas de emergência. Por exemplo, digite o número de telefone do escritório de segurança da empresa de modo que ele receba uma chamada quando uma chamada de emergência é feita. A configuração para **Modo de conferência** determina se o terceiro pode participar ou apenas escutar a chamada. A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:.

- **Modo de conferência** Se você especificou um valor para **URI** de conferência, de definida este campo como um dos seguintes valores:

  - **One-way** Especifica que o terceiro só pode escutar a chamada entre o chamador e o operador PSAP.

  - **Duas vias** Especifica que o terceiro pode participar da chamada entre o chamador e o operador PSAP.

Para obter detalhes sobre os recursos do serviço de emergência do Enterprise Voice, consulte [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de Planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação Operações.


