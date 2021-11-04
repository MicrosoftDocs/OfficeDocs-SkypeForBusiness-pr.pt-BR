---
title: Política de Local Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode configurar políticas de local para determinar se o Enhanced 9-1-1 (E9-1-1) está habilitado e como ele é usado, bem como como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 8f45fefbd13d20e5bdbef2500b17a394f544aad1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764639"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Política de Local: Criar Nova ou Editar Existente

Você pode configurar políticas de local para determinar se o Enhanced 9-1-1 (E9-1-1) está habilitado e como ele é usado, bem como como as informações de local são usadas para usuários e contatos.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de local que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de local requer um nome. As políticas de local global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de local do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de local, o nome não pode ser alterado.

- **Habilitar 9-1-1 (E9-1-1)** Marque essa caixa de seleção para habilitar o E9-1-1 para os usuários que estão atribuídos a essa política de local.

- **Local** Especifique se os usuários são solicitados a obter informações de local:

  - **Obrigatório** Selecione essa opção se os usuários devem ser solicitados a obter informações de local quando seu cliente se registrar em um novo local. Os usuários podem ignorar essa solicitação sem inserir informações de local.

  - **Não obrigatório** Selecione essa opção se os usuários não devem ser solicitados a obter informações de local.

  - **Aviso de isenção de responsabilidade** Selecione essa opção se os usuários devem ser solicitados a obter informações de local, mas verão uma mensagem de aviso de isenção de responsabilidade se recusarem o prompt sem inserir as informações. Os usuários poderão apenas completar uma chamada de emergência até inserirem as informações de local.

- **Usar o local somente para E9-1-1** Marque essa caixa de seleção se as informações de local devem ser usadas somente para chamadas de emergência.

- **Uso de PSTN** Selecione o uso PSTN (rede telefônica pública comutado) que será usado para determinar qual rota de voz será usada para rotear chamadas de emergência de clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo. As opções são **Interna**, **Local** ou **Longa distância**.

- **Número de discagem E9-1-1** Especifique o número discado para chegar aos serviços de emergência.

- **Máscara de discagem E9-1-1** Especifique um número que um usuário disca, que será convertido no número de discagem de emergência. Por exemplo, insira um valor de 212 nesse campo de modo que um usuário possa discar 212 a fim de entrar em contato com os serviços de emergência. Isso permite que números de emergência alternativos sejam discados e ainda assim a chamada chegue aos serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar o número desse país ou região em vez do número do país ou região em que está no momento). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O tamanho máximo da string é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.

    > [!IMPORTANT]
    > Certifique-se de que a máscara de discagem não seja a mesma que o número em um intervalo de números de estacionamento de chamada, pois o roteamento de estacionamento de chamada tem precedência sobre a conversão de string de discagem de emergência. Para ver os intervalos de números do Estacionamento de Chamadas, clique em Recursos de **Voz** na barra de navegação esquerda e clique em **Estacionamento de Chamadas.**

- **URI de notificação** Especifique um ou mais URIs SIP a serem notificados quando uma chamada de emergência for feita. Por exemplo, digite o URI SIP do escritório de segurança da empresa a fim de notificar a equipe de segurança com uma mensagem instantânea sempre que uma chamada de emergência for feita. Se o local do chamador estiver disponível, o local será incluído na notificação. É possível especificar múltiplos URIs SIP como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Também é possível especificar listas de distribuição.

- **URI de conferência** Especifique o URI SIP (número de telefone, nesse caso) para que um terceiro seja conferênciado em chamadas de emergência. Por exemplo, digite o número de telefone do escritório de segurança da empresa de modo que ele receba uma chamada quando uma chamada de emergência é feita. A configuração para **Modo de conferência** determina se o terceiro pode participar ou apenas escutar a chamada. A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:.

- **Modo de conferência** Se você especificou um valor para **o URI** de conferência, de definir este campo como um dos seguintes valores:

  - **One-way** Especifica que o terceiro só pode escutar a chamada entre o chamador e o operador PSAP.

  - **Duas vias** Especifica que o terceiro pode participar da chamada entre o chamador e o operador PSAP.

Para obter detalhes Enterprise Voice recursos e recursos de serviço de emergência, consulte [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) na documentação planejamento. Para obter detalhes sobre como trabalhar com políticas de local, consulte [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) na documentação Operações.