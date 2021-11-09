---
title: Configurar um VTC para Interoperação com Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: Configure os dispositivos VTC para trabalhar com Skype for Business Server.'
ms.openlocfilehash: f3804c0d7f86710fbefa9477d6cf1790b0f16af9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861798"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar um VTC para Interoperação com Skype for Business Server
 
**Resumo:** Configure os dispositivos VTC para trabalhar com Skype for Business Server.
  
Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectará ao servidor Skype for Business VIS por meio de um tronco SIP e gateway de vídeo do Cisco Unified Communications Manager (CallManager ou CUCM).
  
As configurações descritas aqui são destinadas apenas como exemplos de como o CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou usos da funcionalidade CUCM alternativa também podem ser usados para obter o mesmo resultado. Nenhuma recomendação está implícita quanto à configuração ideal para um cenário específico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar um VTC registrado com o CUCM

1. Faça logoff no dispositivo Cisco VTC e navegue até Configuration- \> System Configuration- \> Provisioning.
    
2. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo de provisionamento  <br/> | CUCM <br/> |
   |Endereço ExternalManager  <br/> | FQDN da CUCM <br/> |
   | Domínio ExternalManager <br/> |Domínio cucm  <br/> |
   
3. Navegue até Configuração- \> Configuração do Sistema- \> Rede.
    
4. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome de domínio DNS  <br/> | Nome de domínio do CUCM <br/> |
   |Endereço DNS Server 1  <br/> | seu endereço de servidor DNS desejado <br/> |
   
5. Navegue até Configuração- \> Configuração do Sistema- \> Serviços de Rede. Verifique se o modo H.323 está desligado e o modo SIP está ligado. 
    
6. Essas opções são definidas automaticamente quando o ponto de extremidade é registrado com CUCM. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desligado <br/> |
   |Modo HTTP  <br/> | Habilitado <br/> |
   | Modo SIP <br/> | Habilitado <br/> |
   |Modo Telnet  <br/> | Habilitado <br/> |
   |WelcomeText  <br/> | Ativado <br/> |
   |Modo XMLAPI  <br/> | Habilitado <br/> |
   
7. Navegue até Configuração- \> Configuração do Sistema - \> SIP.
    
8. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Perfil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1 - Saída  <br/> | Desligado <br/> |
   |Perfil 1 - TlsVerify  <br/> | Ativado <br/> |
   |Perfil 1 - Tipo  <br/> | Cisco <br/> |
   |Perfil 1 - URI  <br/> | Atribuído automaticamente no registro CUCM <br/> |
   |Proxy 1 - Endereço  <br/> |O nome de host do CUCM  <br/> |
   
O VTC agora está configurado para interoperação. Antes que o serviço possa começar, há etapas finais para executar no lado cucm.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar dispositivos VTC no CUCM

1. Faça logon no CUCM e navegue até Cisco Unified CM \> Administration- Device- \> Telefone- \> Find. 
    
2. Selecione o dispositivo VTC a ser configurado. Verifique as configurações a seguir na tela Telefone Configuração, corrigindo conforme necessário. Depois que essas configurações foram alteradas ou verificadas, clique em **Salvar**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Informações do dispositivo - Telefone modelo de botão  <br/> | Codec de Telepresence Padrão cisco C40 <br/> |
   |Informações do dispositivo - Perfil Telefone Comum  <br/> | Perfil de Telefone Padrão <br/> |
   |Informações do dispositivo - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do dispositivo - Espaço de Pesquisa de Chamada do AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do dispositivo - Lista de Grupos de Recursos de Mídia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informações específicas do protocolo - Perfil de Segurança do Dispositivo  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Informações específicas do protocolo - Redirecionando o espaço de pesquisa de chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações específicas do protocolo - SUBSCREVER Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Perfil SIP de Informações Específicas do Protocolo  <br/> | Perfil SIP padrão para ponto de extremidade de telepresência <br/> |
   
3. Depois que a configuração do VTC for salva, navegue novamente até a tela Telefone configuração do dispositivo. Na parte superior da tela no grupo Associação, clique na associação para a Interop de Vídeo. Isso traz a tela Configuração de Número de Diretório. 
    
4. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
    Faça as alterações apropriadas conforme mostrado nas Informações de Número do Diretório e no número de diretório Configurações.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   | Informações sobre o número do diretório - Partição de Rota <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Número do diretório Configurações - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |MlPP Alternate Party and Confidential Access Level Configurações - MlPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Linha 1 no dispositivo - Exibição (ID do chamador)  <br/> | Conforme desejado <br/> |
   |Linha 1 no dispositivo - Exibição ASCII (ID do chamador)  <br/> | Conforme desejado <br/> |
   
5. Quando terminar, role até a parte superior da tela e pressione **Salvar**. 
    
A configuração agora está concluída para este dispositivo VTC. Você precisará repetir esse processo para outros dispositivos VTC em sua empresa.

