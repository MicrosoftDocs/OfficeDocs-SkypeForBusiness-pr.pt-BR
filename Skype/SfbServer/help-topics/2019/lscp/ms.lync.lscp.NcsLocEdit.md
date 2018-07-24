---
title: Política de local criar nova ou editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: É possível configurar as políticas de local para determinar se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
ms.openlocfilehash: 41b2a73b40ab9ea1a94d128731917e8a551699b0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006139"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Política de Local: Criar Nova ou Editar Existente
 
É possível configurar as políticas de local para determinar se o 9-1-1 Avançado (E9-1-1) está habilitado e como ele é usado, além de como as informações de local são usadas para usuários e contatos.
  
## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.
  
- **Escopo** Identifica o escopo da política de local que você está criando ou modificando: global, site ou usuário.
    
- **Nome** Cada política de local requer um nome. As políticas de local global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de local do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.
    
    > [!NOTE]
    > Depois de salvar a política de local, o nome não pode ser alterado. 
  
- **Habilitar 9-1-1 avançado (E9-1-1)** Marque esta caixa de seleção para habilitar o E9-1-1 para usuários que estão atribuídos a essa política de local.
    
- **Local** Especifique se os usuários são solicitados a informações de local:
    
  - **Obrigatório** Selecione essa opção se os usuários serão solicitados a fornecer informações de local quando seu cliente se registrar em um novo local. Os usuários podem ignorar essa solicitação sem inserir informações de local.
    
  - **Não é necessário** Selecione essa opção se os usuários não serão solicitados a fornecer informações de local.
    
  - **Isenção de responsabilidade** Selecione essa opção se os usuários devem ser solicitados a fornecer informações de local, mas verão uma mensagem de aviso de isenção se ele recusar o prompt sem digitar as informações. Os usuários poderão apenas completar uma chamada de emergência até inserirem as informações de local.
    
- **Usar o local para E9-1-1 apenas** Marque esta caixa de seleção se as informações de local deve ser usado somente para chamadas de emergência.
    
- **Uso da PSTN** Selecione o uso PSTN (rede) telefônica comutada pública que será usado para determinar qual rota de voz será usada para roteamento de chamadas de emergência de clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo. As opções são **Interna**, **Local** ou **Chamada interurbana**.
    
- **Número de discagem de E9-1-1** Especifique o número discado para acessar os serviços de emergências.
    
- **Máscara de discagem de E9-1-1** Especifique um número discado pelo usuário, que então é traduzido para o número de discagem de emergência. Por exemplo, insira um valor de 212 nesse campo de modo que um usuário possa discar 212 a fim de entrar em contato com os serviços de emergência. Isso permite a números de emergências alternativos para ser discado e ainda têm a chamada acessar os serviços de emergências (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar que o país ou região de número, e não o número para o país ou região que estiverem em). Você pode definir várias máscaras de discagem de emergência, separando os valores com ponto e vírgula. Por exemplo, 212;414. O tamanho máximo da cadeia de caracteres é de 100 caracteres. Cada caractere precisa ser um dígito de 0 a 9.
    
    > [!IMPORTANT]
    > Certifique-se de que a máscara de discagem não seja a mesma que o número em um intervalo de números de estacionamento de chamada, pois o roteamento de estacionamento de chamada tem precedência sobre a conversão da cadeia de caracteres de discagem de emergência. Para ver os intervalos de números do estacionamento de chamada, clique em **Recursos de voz** na barra de navegação à esquerda e clique em **Estacionamento de chamadas**. 
  
- **URI de notificação** Especifique um ou mais URIs de SIP para ser notificado quando for feita uma chamada de emergência. Por exemplo, digite o URI de SIP do escritório de segurança da empresa a fim de notificar a equipe de segurança com uma mensagem instantânea sempre que uma chamada de emergência for feita. Se a localização do chamador estiver disponível, o local é incluído na notificação. É possível especificar vários URIs SIP como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". A cadeia de cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Também é possível especificar listas de distribuição.
    
- **URI de conferência** Especifique o URI do SIP (número de telefone, neste caso) para um terceiro estar envolvidos em chamadas de emergência. Por exemplo, digite o número de telefone do escritório de segurança da empresa de modo que ele receba uma chamada quando uma chamada de emergência é feita. A configuração para  **Modo de conferência** determina se o terceiro pode participar ou apenas escutar a chamada. A cadeia de caracteres precisa ter de 1 a 256 caracteres e precisa começar com o prefixo sip:.
    
- **Modo de conferência** Se você especificou um valor para **URI**de conferência, defina esse campo como um dos seguintes valores:
    
  - **Unidirecional** Especifica que o terceiro pode apenas escutar a chamada entre o chamador e o operador de PSAP.
    
  - **Bidirecional** Especifica que o terceiro pode participar da chamada entre o chamador e o operador de PSAP.
    
Para obter detalhes sobre os recursos de serviço de emergência do Enterprise Voice e recursos, consulte [Visão geral do E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com políticas de localização, consulte [Configurando a política de local](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) na documentação operações.
  

