---
title: Implantar serviços de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implantar o E9-1-1 no Skype for Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
ms.openlocfilehash: 4373797b8a96f83100a39735cf20b51558eb15d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291267"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Implantar serviços de emergência no Skype for Business Server
 
Implantar o E9-1-1 no Skype for Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
  
O 9-1-1 aprimorado (E9-1-1) é um recurso de notificação de emergência que associa o número de telefone da pessoa que está chamando a um endereço cívico ou um endereço de rua. Usando essas informações, o PSAP (Ponto de Atendimento de Segurança Pública) consegue expedir imediatamente os serviços de emergência para o chamador com problemas.
  
Para dar suporte ao E9-1-1, o Skype for Business Server deve poder associar corretamente um local a um cliente e garantir que essas informações sejam usadas para direcionar a chamada de emergência para o PSAP mais próximo.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Pré-requisitos de implantação para E9-1-1

Antes de implantar o E9-1-1, você já deve ter implantado seus servidores internos do Skype for Business Server, incluindo um repositório de gerenciamento central, um pool de front-ends ou um servidor Standard Edition. Você também deve implantar um ou mais servidores de mediação, autônomos ou posicionados com servidores front-end. Além disso, uma implantação do E9-1-1 exige um tronco SIP para um provedor de serviços de E9-1-1 qualificado ou um gateway ELIN (Número de Identificação de Local de Emergência) para sua PSTN (Rede Telefônica Pública Comutada).
  
## <a name="deployment-process"></a>Processo de implantação

A tabela a seguir fornece uma visão geral do processo de implantação de E9-1-1.
  
|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Definir utilização de voz, rotas e configurações de tronco  <br/> |1. criar um novo registro de uso PSTN. Este é o mesmo nome utilizado para a configuração de **Uso do PSTN** na política de local. <br/> 2. crie ou atribua uma rota de voz para o registro de uso PSTN criado na etapa anterior e, em seguida, aponte o atributo gateway para o E9-1-1 trunk ou gateway ELIN.  <br/> 3. para um provedor de serviços de tronco SIP E9-1-1, defina o tronco que tratará E9-1-1 chamadas pelo SIP para passar dados PIDF-LO usando o cmdlet **set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. opcionalmente, para um provedor de serviços E9 de tronco SIP-1-1, crie ou atribua uma rota PSTN local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviço do E9-1-1. Essa rota será usada se a conexão com o provedor de serviços de E9-1-1 não estiver disponível. Se houver suporte para o provedor de serviços de E9-1-1, atribua uma regra de configuração de tronco ao gateway que converte a cadeia de caracteres de discagem 911 no número DID (discagem direta interna) do ECRC (Centro de resposta de chamada de emergência) nacional.  <br/> |CSVoiceAdmin  <br/> |[Configurar uma rota de voz E9-1-1 no Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Criar políticas locais e atribuí-las aos usuários e sub-redes  <br/> |1. Examine a política de localização global.  <br/> 2. Crie uma política de localização com um escopo de nível de usuário; ou, se a organização tiver mais de um site com diferentes usos de emergência, crie uma política de localização com um escopo de nível de rede.  <br/> 3. atribua a política de localização a sites de rede.  <br/> 4. Adicione as sub-redes adequadas ao site de rede.  <br/> 5. (opcional) atribua a política de localização a políticas de usuário.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (exceto para a criação de Políticas de Local)  <br/> |[Criar políticas de localização no Skype for Business Server](create-location-policies.md) <br/> [Adicionar uma política de localização a um site de rede no Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurar o banco de dados de localização  <br/> |1. Preencha o banco de dados com um mapeamento de elementos de rede para locais.  <br/> 2. para gateways do ELIN, adicione o ELINs à \<coluna\> CompanyName.  <br/> 3. Configure a conexão com o provedor de serviços E9-1-1 para validar os endereços.  <br/> 4. valide os endereços com o provedor de serviços E9-1-1.  <br/> 5. publique o banco de dados atualizado.  <br/> 6. para os gateways do ELIN, carregue o ELINs para o banco de dados de identificação de localização automática (ALI) da sua operadora PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar o banco de dados de localização no Skype for Business Server](configure-the-location-database.md) <br/> |
|Configure os Recursos Avançados (opcional)  <br/> |1. Configure a URL para o aplicativo SNMP.  <br/> 2. Configure a URL para o local do serviço de informações de localização secundário.  <br/> |CSVoiceAdmin  <br/> |[Configurar um aplicativo SNMP no Skype for Business Server](configure-an-snmp-application.md) <br/> [Configurar um serviço de informações de localização secundário no Skype for Business Server](secondary-location-information-service.md) <br/> |
   

