---
title: Implantar E9-1-1 no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implante o E9-1-1 em Skype para o Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
ms.openlocfilehash: 0994bb3b1c0cd5b4c4ce1dcc1c0a46b4e97b76b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>Implantar E9-1-1 no Skype for Business Server 2015
 
Implante o E9-1-1 em Skype para o Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
  
9-1-1 avançado (E9-1-1) é um recurso de notificação de emergência que associa o número de telefone do chamador um residenciais ou um endereço. Usando essas informações, o PSAP (Ponto de Atendimento de Segurança Pública) consegue expedir imediatamente os serviços de emergência para o chamador com problemas.
  
Para suportar o E9-1-1, Skype para Business Server deve ser capaz de associar corretamente um local com um cliente e certifique-se de que essas informações são usadas para rotear a chamada de emergência para o PSAP mais próximo.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Pré-requisitos de implantação para E9-1-1

Antes de implantar o E9-1-1, você já deve ter implantado sua Skype para servidores internos do Business Server, incluindo um repositório de gerenciamento Central, um pool de Front-End ou um servidor Standard Edition. Você também deve implantar um ou mais servidores de mediação, ambos autônomos ou colocados com servidores Front-End. Além disso, uma implantação do E9-1-1 exige um tronco SIP para um provedor de serviços de E9-1-1 qualificado ou um gateway ELIN (Número de Identificação de Local de Emergência) para sua PSTN (Rede Telefônica Pública Comutada).
  
## <a name="deployment-process"></a>Processo de implantação

A tabela a seguir fornece uma visão geral do processo de implantação de E9-1-1.
  
|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Definir utilização de voz, rotas e configurações de tronco  <br/> |1. Crie um novo registro de uso do PSTN. Este é o mesmo nome utilizado para a configuração de **Uso do PSTN** na política de local. <br/> 2. Crie ou atribua uma rota de voz ao registro de uso do PSTN criado na etapa anterior e aponte o atributo gateway ao tronco SIP do E9-1-1 ou gateway ELIN.  <br/> 3. para um provedor de serviço de E9-1-1 de tronco SIP, defina o tronco que manipulará as chamadas de E9-1-1 sobre o SIP para passar os dados de PIDF-LO usando o cmdlet **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. opcionalmente, para um provedor de serviço de E9-1-1 de tronco SIP, crie ou atribua uma rota local de PSTN para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1. Essa rota será usada se a conexão com o provedor de serviços de E9-1-1 não estiver disponível. Se houver suporte para o provedor de serviços de E9-1-1, atribua uma regra de configuração de tronco ao gateway que converte a cadeia de caracteres de discagem 911 no número DID (discagem direta interna) do ECRC (Centro de resposta de chamada de emergência) nacional.  <br/> |CSVoiceAdmin  <br/> |[Configurar uma rota de voz do E9-1-1 no Skype para Business Server 2015](configure-an-e9-1-1-voice-route.md) <br/> |
|Criar políticas locais e atribuí-las aos usuários e sub-redes  <br/> |1. Revise a política de local global.  <br/> 2. criar uma política de local com um escopo no nível do usuário; ou, se a organização tiver mais de um site com usos de emergência diferentes, crie uma política de local com um escopo no nível de rede.  <br/> 3. atribua a política de local aos sites de rede.  <br/> 4. Adicione as sub-redes apropriadas ao site de rede.  <br/> 5. (opcional) atribua a política local às políticas de usuário.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (exceto para a criação de Políticas de Local)  <br/> |[Criar políticas de local no Skype para Business Server 2015](create-location-policies.md) <br/> [Adicionar uma política de local a um site de rede no Skype para Business Server 2015](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar o banco de dados de localização  <br/> |1. preencha o banco de dados com um mapeamento de elementos de rede para locais.  <br/> 2. para gateways ELIN, adicione os ELINs para o \<CompanyName\> coluna.  <br/> 3. configure a conexão para o provedor de serviço E9-1-1 para validar endereços.  <br/> 4. valide os endereços com o provedor de serviço E9-1-1.  <br/> 5. publica o banco de dados atualizado.  <br/> 6. para gateways ELIN, carregue os elins no banco de dados de identificação de local automática (ALI) da sua operadora da PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar o banco de dados local no Skype para Business Server 2015](configure-the-location-database.md) <br/> |
|Configure os Recursos Avançados (opcional)  <br/> |1. configure a URL do aplicativo SNMP.  <br/> 2. configure a URL para o local do serviço de informações de localização secundária.  <br/> |CSVoiceAdmin  <br/> |[Configurar um aplicativo SNMP no Skype para Business Server 2015](configure-an-snmp-application.md) <br/> [Configurar um serviço de informações de localização secundário no Skype para Business Server 2015](secondary-location-information-service.md) <br/> |
   

