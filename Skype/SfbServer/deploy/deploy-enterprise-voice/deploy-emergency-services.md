---
title: Implantar serviços de emergência no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Implante o E9-1-1 no Skype for Business Server Enterprise Voice. Inclui pré-requisitos e lista de verificação do processo de implantação.
---

# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Implantar serviços de emergência no Skype for Business Server
 
Implante o E9-1-1 no Skype for Business Server Enterprise Voice. Inclui pré-requisitos e lista de verificação do processo de implantação.
  
O 9-1-1 aprimorado (E9-1-1) é um recurso de notificação de emergência que associa o número de telefone do chamador a um endereço cívico ou de rua. Usando essas informações, o PSAP (Ponto de Atendimento de Segurança Pública) consegue expedir imediatamente os serviços de emergência para o chamador com problemas.
  
Para dar suporte ao E9-1-1, o Skype for Business Server deve ser capaz de associar corretamente um local a um cliente e garantir que essas informações sejam usadas para rotear a chamada de emergência para o PSAP mais próximo.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Pré-requisitos de implantação para E9-1-1

Antes de implantar o E9-1-1, você já deve ter implantado seus servidores internos do Skype for Business Server, incluindo um armazenamento de Gerenciamento Central, um pool de Front-End ou um servidor Edição Standard. Você também deve implantar um ou mais Servidores de Mediação, autônomos ou alocados com Servidores Front-End. Além disso, uma implantação do E9-1-1 exige um tronco SIP para um provedor de serviço de E9-1-1 certificado ou um gateway ELIN (Emergency Location Identification Number) para seu PSTN (Rede telefônica comutada pública).
  
## <a name="deployment-process"></a>Processo de implantação

A tabela a seguir fornece uma visão geral do processo de implantação de E9-1-1.
  
|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Definir utilização de voz, rotas e configurações de tronco  <br/> |1. Crie um novo registro de uso PSTN. Este é o mesmo nome utilizado para a configuração de **Uso do PSTN** na política local. <br/> 2. Crie ou atribua uma rota de voz ao registro de uso PSTN criado na etapa anterior e aponte o atributo gateway para o tronco SIP do E9-1-1 ou gateway ELIN.  <br/> 3. Para um provedor de serviço E9-1-1 de tronco SIP, de definir o tronco que manipulará chamadas E9-1-1 sobre o SIP para passar dados PIDF-LO usando o cmdlet **Set-CsTrunkConfiguration -EnablePIDFLOSupport** . <br/> 4. Opcionalmente, para um provedor de serviços do tronco SIP E9-1-1, crie ou atribua uma rota PSTN local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1. Esta rota será usada se a conexão com o provedor de serviço de E9-1-1 não estiver disponível. Se o provedor de serviço de E9-1-1 for suportado, atribua uma regra de configuração de tronco ao gateway que converte a cadeia de caracteres de discagem 911 no número DID (discagem direta interna) do ECRC (Centro de resposta de chamada de emergência) nacional.  <br/> |CSVoiceAdmin  <br/> |[Configurar uma rota de voz E9-1-1 no Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Criar políticas locais e atribuí-las aos usuários e sub-redes  <br/> |1. Revise a política de local global.  <br/> 2. Crie uma política de local com um escopo no nível do usuário; ou, se a organização tiver mais de um site com diferentes usos de emergência, crie uma política de local com um escopo de nível de rede.  <br/> 3. Atribua a política de local a sites de rede.  <br/> 4. Adicione as sub-redes apropriadas ao site de rede.  <br/> 5. (Opcional) Atribua a política de local às políticas do usuário.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (exceto para a criação de Políticas de Local)  <br/> |[Criar políticas de localização em Skype for Business Server](create-location-policies.md) <br/> [Adicionar uma política de local a um site de rede Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configure o banco de dados de localização  <br/> |1. Preencha o banco de dados com um mapeamento de elementos de rede para locais.  <br/> 2. Para gateways ELIN, adicione os ELINs à \<CompanyName\> coluna.  <br/> 3. Configure a conexão com o provedor de serviços E9-1-1 para validar endereços.  <br/> 4. Valide os endereços com o provedor de serviços E9-1-1.  <br/> 5. Publique o banco de dados atualizado.  <br/> 6. Para gateways ELIN, carregue os ELINs no banco de dados ALI (Identificação Automática de Localização) da operadora PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurar o banco de dados de localização em Skype for Business Server](configure-the-location-database.md) <br/> |
|Configure os Recursos Avançados (opcional)  <br/> |1. Configure a URL do aplicativo SNMP.  <br/> 2. Configure a URL para o local do serviço Informações de Localização Secundária.  <br/> |CSVoiceAdmin  <br/> |[Configurar um aplicativo SNMP no Skype for Business Server](configure-an-snmp-application.md) <br/> [Configurar um serviço secundário de Informações de Localização Skype for Business Server](secondary-location-information-service.md) <br/> |
   

