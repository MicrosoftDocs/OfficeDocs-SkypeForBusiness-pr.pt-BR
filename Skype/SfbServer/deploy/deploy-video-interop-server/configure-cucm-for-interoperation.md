---
title: Configurar o CUCM para interoperação com o Skype for Business Server
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumo: Configure o CUCM para funcionar com o Skype for Business Server.'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837111"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar o CUCM para interoperação com o Skype for Business Server
 
**Resumo:** Configure o CUCM para funcionar com o Skype for Business Server.
  
> [!CAUTION]
> Esse recurso é testado com a versão 10.5 do Cisco Unified Communications Manager (CallManager ou CUCM) usando apenas a instalação de Troncos em TCP. Verifique se o ambiente do CUCM atende a esses critérios antes de prosseguir. 
  
As configurações descritas aqui são apenas exemplos de como o CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou usos de funcionalidades alternativas do CUCM também podem ser usadas para obter o mesmo resultado. Nenhuma recomendação está implícita quanto à configuração ideal para um cenário específico.
  
Várias configurações do CUCM precisam ser confirmadas ou alteradas para interoperação com o VIS. Siga os procedimentos abaixo para evitar a falta das configurações necessárias.
  
### <a name="configure-the-cucm"></a>Configurar o CUCM

1. Faça logon no CUCM e navegue até Administração do Cisco Unified CM - \> Roteamento de Chamadas - Classe de \> Controle- \> Partição.
    
2. Na tela Configuração da Partição, insira o nome e a descrição da partição e clique em **Adicionar Novo.**
    
3. Navegue até Administração do Cisco Unified CM - \> Roteamento de Chamadas - \> Classe de Controle - Espaço de Pesquisa de \> Chamada.
    
4. Na tela Configuração do Espaço de Pesquisa de Chamada, insira o nome do espaço de pesquisa de chamada e, em Partições Selecionadas, insira o nome da partição que você acabou de criar. Clique **em Salvar** quando terminar.
    
5. Navegue até Administração do Cisco Unified CM - \> Sistema - Segurança - Perfil de Segurança de Tronco \> \> SIP.
    
6. Na tela Configuração do Perfil de Segurança do Tronco SIP, de definidas as opções de Informações do Perfil de Segurança do Tronco SIP, conforme mostrado, e clique em **Adicionar Novo.**
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de Segurança do Dispositivo  <br/> |Não Seguro  <br/> |
   |Tipo de Transporte de Entrada  <br/> |TCP + UDP  <br/> |
   |Tipo de Transporte de Saída  <br/> |TCP  <br/> |
   |Porta de entrada  <br/> |5060  <br/> |
   
7. Navegue até Administração do Cisco Unified CM - \> Dispositivo- \> Configurações do Dispositivo - \> Perfil SIP.
    
8. Na tela Configuração do Perfil SIP, de definidas as opções de Informações do Perfil SIP, conforme mostrado. 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrição  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Na mesma tela, role para baixo até a seção Informações de Perfil SDP. A **opção Modificador de** Largura de Banda em nível de sessão SDP para Oferta Antecipada e Convites é definida por padrão como TIAS e AS. Altere essa opção para TIAS somente. Se você deixar essa opção na configuração padrão, o Skype for Business Server não compreenderá as informações do modificador de largura de banda na mensagem SIP. TIAS significa Transport Independent Application Specific enquanto AS significa Application Specific. Estas são as opções SIP especificadas na RFC3890.
    
10. Na mesma tela, role para baixo ainda mais. Na Configuração Específica do Tronco  do Perfil SIP, selecione Suporte de Oferta Antecipada para chamadas de voz e vídeo e de definida como a opção obrigatória **(inserir MTP,** se necessário). Isso permitirá que o CUCM de configurar uma chamada SIP de saída com Early Offer. Um novo recurso no CUCM 8.5 e além é que ele dá suporte à configuração de chamada de saída com Early Offer sem exigir o Ponto de Terminação de Mídia (MTP).
    
11. Verifique se, na seção ping de Opções SIP, a caixa está marcada ao lado de "Habilitar PING DE OPÇÕES para monitorar o status de destino de Troncos com o Tipo de Serviço 'Nenhum (Padrão)'."
    
12. Quando terminar, clique em **Adicionar Novo.**
    
13. Navegue até Administração do Cisco Unified CM - \> Dispositivo- \> Tronco. 
    
14. De definir o protocolo do dispositivo como SIP e pressione **Next**.
    
15. Em Informações do Dispositivo, de definir o Nome e a Descrição do Dispositivo (provavelmente como SfBVideoInterop_SIPTrunk) e a Lista de Grupos de Recursos de Mídia como um MRGL que contenha os recursos de mídia corretos. 
    
16. Role para baixo ainda mais. O Ponto de Terminação de Mídia (MTP) não é necessário para Chamadas de Vídeo, caso ainda não tenha sido desmarcado, desmarque-o. Marque a opção Executar **em todos os nós de CM unificados ativos.** Observe que você deve adicionar todos os nós do CUCM à configuração do Skype for Business Server.
    
17. Role para baixo ainda mais. De definidas as opções de Chamadas de Entrada e Configurações de Terceiros Conectados, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Espaço de Pesquisa de Chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de transformação de partes conectadas  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Role para baixo ainda mais. Na seção Destino das Informações SIP da configuração do Tronco SIP, especifique o FQDN do Pool de VIS ou o endereço IP de servidores VIS individuais no pool (adicionando várias entradas). Na Porta de Destino, especifique a Porta na qual o VIS está escutando para conexões do CUCM (o padrão é 6001). Também especifique o perfil de segurança do Tronco SIP e o perfil SIP que você criou anteriormente, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Perfil de Segurança de Tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Re-redirecionando o espaço de pesquisa de chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de pesquisa de chamada de referência fora da caixa de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de sinalização DTMF  <br/> |RFC 2833  <br/> |
   
19.  Role para baixo ainda mais. De definir as Informações de Gravação conforme apropriado para o seu sistema. Não há problema em deixá-lo definido como **Nenhum.** 
    
20. Quando terminar, clique em **Adicionar Novo.**
    
21. Navegue até Administração do Cisco Unified CM – \> Roteamento de Chamadas - \> Rota/Rota - \> Padrão de Rota.
    
22. Na tela Configuração de Padrão de Rota, insira os parâmetros de definição de padrão mostrados abaixo. Role para baixo até a seção Transformações de Terceiros Chamados, de definida como mostrado e clique em **Adicionar Novo** quando terminar.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Padrão de Rota  <br/> |7779999  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrição  <br/> |Partição para SfBVideoInterop  <br/> |
    |Lista de gateway/rota  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de Transformação de Parte Chamada  <br/> |+14257779999  <br/> |
   
23. Navegue até Administração do Cisco Unified CM - \> Roteamento de Chamadas - \> Padrão de Rota SIP.
    
24. Na tela Configuração do Padrão de Rota SIP, de definidas as opções de Definição de Padrão, conforme mostrado, e clique em **Adicionar Novo.**
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    | Uso do padrão <br/> |Roteamento de Domínio  <br/> |
    |Padrão IPv4  <br/> |contoso.com (deixar em branco se estiver usando IPv6)  <br/> |
    |Padrão IPv6  <br/> |contoso.com (deixar em branco se estiver usando IPv4)  <br/> |
    |Descrição  <br/> |Padrão SIPRoute para mediarv  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de troncos/rotas SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Caixa de seleção Padrão de Bloqueio  <br/> |deixar desmarcado  <br/> |
   
25. Se você tiver alterado as taxas de bits de áudio ou vídeo das configurações padrão, será necessário devolvê-las para os padrões. Para definir a taxa de bits para chamadas de Áudio/Vídeo, navegue até Administração do Cisco Unified CM- \> Informações do \> Sistema- Região- \> Região. Os padrões são mostrados abaixo para referência:
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Região  <br/> |Padrão  <br/> |
    |Lista de preferências de codec de áudio  <br/> |Padrão do sistema  <br/> |
    |Taxa máxima de bits de áudio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Taxa máxima de bits de sessão para chamadas de vídeo  <br/> |200000 kbps  <br/> |
    |Taxa de bits máxima da sessão  <br/> |2000000000 kbps  <br/> |
   
Neste ponto, o gateway de vídeo do CUCM está configurado para funcionar com o VIS. A configuração correspondente precisará ser feita em cada VTC que você deseja integrar.
> [!NOTE]
> Para melhorar a resiliência, você pode configurar esse gateway CUCM para funcionar com um segundo Servidor de Interop de Vídeo ou pool de VIS. Consulte [Mecanismos de resiliência para](../../plan-your-deployment/video-interop-server.md#resiliency) obter mais informações.
  
## <a name="see-also"></a>Confira também

[Configurar um VTC para interoperação com o Skype for Business Server](configure-a-vtc-for-interoperation.md)
