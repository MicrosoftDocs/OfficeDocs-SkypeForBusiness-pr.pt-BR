---
title: Configurar um VTC para interoperação com o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: configurar os dispositivos VTC para que funcionem com o Skype for Business Server.'
ms.openlocfilehash: b266c8cc97898fe192ec023183a565b921d86949
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798078"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar um VTC para interoperação com o Skype for Business Server
 
**Resumo:** Configure os dispositivos VTC para que funcionem com o Skype for Business Server.
  
Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectarão ao servidor do Skype for Business VIS por meio de um tronco SIP e do gateway de vídeo do Cisco Unified Communications Manager (CallManager ou CUCM).
  
As configurações descritas aqui servem apenas como exemplos de como o CUCM pode ser configurado para trabalhar com um VIS. Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado. Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar um VTC registrado no CUCM

1. Conecte-se ao dispositivo Cisco VTC e navegue até configuração-\>configuração do sistema\>-provisionamento.
    
2. Verifique as seguintes configurações e faça as correções, conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo de Provisionamento  <br/> | CUCM <br/> |
   |Endereço ExternalManager  <br/> | FQDN do CUCM <br/> |
   | Domínio externalmanager <br/> |Domínio do CUCM  <br/> |
   
3. Navegue até configuração-\>sistema-configuração\>do sistema-rede.
    
4. Verifique as seguintes configurações e faça as correções, conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome do Domínio DNS  <br/> | Nome do Domínio do CUCM <br/> |
   |Endereço do Servidor DNS  <br/> | Endereço do servidor DNS desejado <br/> |
   
5. Navegue até configuração-\>sistema-configuração\>do sistema-serviços de rede. Verifique se o modo H.323 está desativado e se o modo SIP está ativado. 
    
6. Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM. Verifique as seguintes configurações e faça as correções, conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desativado <br/> |
   |Modo HTTP  <br/> | Ativado <br/> |
   | Modo SIP <br/> | Ativado <br/> |
   |Modo Telnet  <br/> | Ativado <br/> |
   |Texto de Boas-vindas  <br/> | Ativado <br/> |
   |Modo XMLAPI  <br/> | Ativado <br/> |
   
7. Navegue até configuração-\>sistema-configuração\>do sistema-SIP.
    
8. Verifique as seguintes configurações e faça as correções, conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Perfil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1 - Saída  <br/> | Desativado <br/> |
   |Perfil 1-TlsVerify  <br/> | Ativado <br/> |
   |Perfil 1 - Tipo  <br/> | Cisco <br/> |
   |Perfil 1 - URI  <br/> | Atribuído automaticamente durante o registro no CUCM <br/> |
   |Proxy 1 - Endereço  <br/> |O nome de host do CUCM  <br/> |
   
Agora o VTC está configurado para interoperação. Antes de o serviço iniciar, é necessário executar algumas etapas finais no CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar os dispositivos VTC no CUCM

1. Conecte-se ao CUCM e navegue até a administração do Gerenciador\>de telefonia\>unificado da Cisco-Device-Phone-\>Find. 
    
2. Selecione o dispositivo VTC a ser configurado. Verifique as seguintes configurações na tela Configuração do Telefone, fazendo as correções necessárias. Depois que essas configurações forem alteradas ou configuradas, clique em **Salvar**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Informações do Dispositivo - Modelo de Botão de Telefone  <br/> | Codec padrão de telepresença Cisco C40 <br/> |
   |Informações do Dispositivo - Perfil de Telefone Comum  <br/> | Perfil de Telefone Comum Padrão <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Lista de Grupos de Recursos de Mídia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo  <br/> | Codec de telepresença Cisco C40 <br/> |
   |Informações Específicas do Protocolo - Reencaminhamento do Espaço de Pesquisa de de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações específicas do protocolo-assinar o espaço de pesquisa de chamadas  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil SIP  <br/> | Perfil SIP Padrão para o Ponto de Extremidade de Telepresença <br/> |
   
3. Assim que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo. Na parte superior da tela, no grupo Associação, clique na associação correspondente à Interoperabilidade de Vídeo. Como resultado, a tela Configuração do Número de Diretório será exibida. 
    
4. Verifique as seguintes configurações e faça as correções necessárias: 
    
    Faça as alterações adequadas nas Informações do Número de Diretório e nas Configurações do Número de Diretório, conforme mostrado.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   | Informações do Número de Diretório - Partição de Rota <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Configurações do Número de Diretório - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Configurações de Nível de Acesso Confidencial e Parte Alternativa MLPP - Espaço de Pesquisa de Chamada MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Linha 1 em Device-display (identificação de chamadas)  <br/> | Conforme desejado <br/> |
   |Linha 1 na exibição dispositivo-ASCII (identificação de chamadas)  <br/> | Conforme desejado <br/> |
   
5. Quando terminar, role até a parte superior da tela e pressione **Salvar**. 
    
Agora a configuração do dispositivo VTC foi concluída. Você precisará repetir esse processo para outros dispositivos VTC de sua empresa.

