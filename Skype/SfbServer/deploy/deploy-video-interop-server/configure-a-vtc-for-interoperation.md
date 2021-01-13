---
title: Configurar um VTC para interoperação com o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: configure os dispositivos VTC para trabalhar com o Skype for Business Server.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802071"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurar um VTC para interoperação com o Skype for Business Server
 
**Resumo:** Configure os dispositivos VTC para trabalhar com o Skype for Business Server.
  
Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectará ao servidor VIS do Skype for Business por meio de um tronco SIP e gateway de vídeo cisco Unified Communications Manager (CallManager ou CUCM).
  
As configurações descritas aqui são apenas exemplos de como o CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou usos de funcionalidades alternativas do CUCM também podem ser usadas para obter o mesmo resultado. Nenhuma recomendação está implícita quanto à configuração ideal para um cenário específico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurar um VTC registrado no CUCM

1. Faça logoff no dispositivo Cisco VTC e navegue até Configuração - \> Configuração do Sistema \> - Provisionamento.
    
2. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo de provisionamento  <br/> | CUCM <br/> |
   |Endereço ExternalManager  <br/> | FQDN do CUCM <br/> |
   | Domínio ExternalManager <br/> |Domínio do CUCM  <br/> |
   
3. Navegue até Configuração - \> Configuração do Sistema - \> Rede.
    
4. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome de domínio DNS  <br/> | Nome de domínio do CUCM <br/> |
   |Endereço dns server 1  <br/> | seu endereço de servidor DNS desejado <br/> |
   
5. Navegue até Configuração - \> Configuração do Sistema - \> Serviços de Rede. Verifique se o modo H.323 está desligado e o modo SIP está ligado. 
    
6. Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Modo H.323  <br/> | Desabilitado <br/> |
   |Modo HTTP  <br/> | Habilitado <br/> |
   | Modo SIP <br/> | Habilitado <br/> |
   |Modo Telnet  <br/> | Habilitado <br/> |
   |WelcomeText  <br/> | Habilitado <br/> |
   |Modo XMLAPI  <br/> | Habilitado <br/> |
   
7. Navegue até Configuração - \> Configuração do Sistema - \> SIP.
    
8. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Perfil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Perfil 1 - Saída  <br/> | Desabilitado <br/> |
   |Perfil 1 - TlsVerify  <br/> | Habilitado <br/> |
   |Perfil 1 - Tipo  <br/> | Cisco <br/> |
   |Perfil 1 - URI  <br/> | Atribuído automaticamente no registro CUCM <br/> |
   |Proxy 1 - Endereço  <br/> |O nome de host do CUCM  <br/> |
   
O VTC agora está configurado para interoperação. Antes que o serviço possa começar, há etapas finais para executar no lado do CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurar dispositivos VTC no CUCM

1. Faça logon no CUCM e navegue até Administração do Cisco Unified CM - \> Dispositivo- \> Telefone- \> Encontrar. 
    
2. Selecione o dispositivo VTC a ser configurado. Verifique as seguintes configurações na tela Configuração do Telefone, corrigindo conforme necessário. Depois que essas configurações foram alteradas ou verificadas, clique em **Salvar.**
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Informações do Dispositivo - Modelo de Botão de Telefone  <br/> | Codec de Telepresência da Cisco C40 padrão <br/> |
   |Informações do Dispositivo - Perfil de Telefone Comum  <br/> | Perfil de Telefone Comum Padrão <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações do Dispositivo - Lista de Grupos de Recursos de Mídia  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Informações Específicas do Protocolo - Redirecionando o Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Espaço de Pesquisa de Chamada SUBSCRIBE  <br/> | CSS_SfBVideoInterop <br/> |
   |Informações Específicas do Protocolo - Perfil SIP  <br/> | Perfil SIP padrão para o ponto de extremidade de telepresência <br/> |
   
3. Depois que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo. Na parte superior da tela do grupo Associação, clique na associação para a Interop de Vídeo. Isso exibe a tela Configuração do Número de Diretório. 
    
4. Verifique as seguintes configurações, corrigindo conforme necessário: 
    
    Faça as alterações apropriadas, conforme mostrado nas Informações do Número de Diretório e nas Configurações do Número de Diretório.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   | Informações de Número de Diretório - Partição de Rota <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Configurações de Número de Diretório - Espaço de Pesquisa de Chamada  <br/> | CSS_SfBVideoInterop <br/> |
   |Configurações de Nível de Acesso Confidencial e de Terceiros Alternativos MLPP - Espaço de Pesquisa de Chamada MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Linha 1 no dispositivo - Exibição (ID do chamador)  <br/> | Conforme desejado <br/> |
   |Linha 1 no dispositivo - Exibição ASCII (ID do chamador)  <br/> | Conforme desejado <br/> |
   
5. Quando terminar, role até a parte superior da tela e pressione **Save**. 
    
A configuração agora está concluída para este dispositivo VTC. Você precisará repetir esse processo para outros dispositivos VTC em sua empresa.

