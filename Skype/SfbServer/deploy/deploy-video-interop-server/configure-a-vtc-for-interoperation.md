---
title: Configurar um VTC para interoperação com o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: Configure os dispositivos VTC para trabalhar com Skype para Business Server 2015.'
ms.openlocfilehash: a88f34866a2a2147be0f30488e961552c6f19350
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server-2015"></a>Configurar um VTC para interoperação com o Skype for Business Server 2015
 
**Resumo:** Configure os dispositivos VTC para trabalhar com Skype para Business Server 2015.
  
Você precisará executar os seguintes procedimentos de configuração para cada VTC que será conectado ao servidor VIS do Skype for Business por meio de um tronco SIM e de um gateway de vídeo CUCM.
  
As configurações descritas aqui servem apenas como exemplos de como CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado. Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar um VTC registrado no CUCM

1. Faça logon no dispositivo Cisco VTC e navegue até configuração -\>configuração do sistema -\>provisionamento.
    
2. Verifique as seguintes configurações e faça as correções necessárias: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo de Provisionamento  <br/> | CUCM <br/> |
   |Endereço ExternalManager  <br/> | FQDN do CUCM <br/> |
   | Domínio ExternalManager <br/> |Domínio do CUCM  <br/> |
   
3. Navegue até configuração -\>configuração do sistema -\>rede.
    
4. Verifique as seguintes configurações e faça as correções necessárias: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome do Domínio DNS  <br/> | Nome do Domínio do CUCM <br/> |
   |Endereço do Servidor DNS  <br/> | Endereço do servidor DNS desejado <br/> |
   
5. Navegue até configuração -\>configuração do sistema -\>serviços de rede. Verifique se o modo H.323 está desativado e se o modo SIP está ativado. 
    
6. Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM. Verifique as seguintes configurações e faça as correções, conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desativado <br/> |
   |Modo HTTP  <br/> | Ativado <br/> |
   | Modo SIP <br/> | Ativado <br/> |
   |Modo Telnet  <br/> | Ativado <br/> |
   |WelcomeText  <br/> | Ativado <br/> |
   |Modo XMLAPI  <br/> | Ativado <br/> |
   
7. Navegue até configuração -\>configuração do sistema -\>SIP.
    
8. Verifique as seguintes configurações e faça as correções necessárias: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Perfil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1 - Saída  <br/> | Desativado <br/> |
   |Perfil 1 - TlsVerify  <br/> | Ativado <br/> |
   |Perfil 1 - Tipo  <br/> | Cisco <br/> |
   |Perfil 1 - URI  <br/> | Atribuído automaticamente durante o registro no CUCM <br/> |
   |Proxy 1 - Endereço  <br/> |O nome de host do CUCM  <br/> |
   
Agora o VTC está configurado para interoperação. Antes de o serviço iniciar, é necessário executar algumas etapas finais no CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar os dispositivos VTC no CUCM

1. Faça logon em CUCM e navegue até Cisco Unified CM administração -\>dispositivo -\>telefone -\>localizar. 
    
2. Selecione o dispositivo VTC a ser configurado. Verifique as seguintes configurações na tela Configuração do Telefone, fazendo as correções necessárias. Depois que essas configurações forem alteradas ou configuradas, clique em **Salvar**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Informações do Dispositivo - Modelo de Botão de Telefone  <br/> | Cisco Standard Codec de telepresença C40 <br/> |
   |Informações do Dispositivo - Perfil de Telefone Comum  <br/> | Perfil de Telefone Comum Padrão <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Lista de Grupos de Recursos de Mídia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo  <br/> | Cisco telepresença Codec C40 <br/> |
   |Informações Específicas do Protocolo - Reencaminhamento do Espaço de Pesquisa de de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações específicas de protocolo - inscrever-se chamar o espaço de pesquisa  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil SIP  <br/> | Perfil SIP Padrão para o Ponto de Extremidade de Telepresença <br/> |
   
3. Assim que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo. Na parte superior da tela, no grupo Associação, clique na associação correspondente à Interoperabilidade de Vídeo. Como resultado, a tela Configuração do Número de Diretório será exibida. 
    
4. Verifique as seguintes configurações e faça as correções necessárias: 
    
    Faça as alterações adequadas nas Informações do Número de Diretório e nas Configurações do Número de Diretório, conforme mostrado.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   | Informações do Número de Diretório - Partição de Rota <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Configurações do Número de Diretório - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Configurações de Nível de Acesso Confidencial e Parte Alternativa MLPP - Espaço de Pesquisa de Chamada MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Linha 1 no dispositivo - exibição (ID de chamador)  <br/> | Conforme desejado <br/> |
   |Linha 1 no dispositivo - exibição ASCII (ID de chamador)  <br/> | Conforme desejado <br/> |
   
5. Quando terminar, role até a parte superior da tela e pressione **Salvar**. 
    
Agora a configuração do dispositivo VTC foi concluída. Você precisará repetir esse processo para outros dispositivos VTC de sua empresa.

