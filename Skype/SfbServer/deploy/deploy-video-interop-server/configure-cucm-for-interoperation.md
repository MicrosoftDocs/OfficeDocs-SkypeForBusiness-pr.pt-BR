---
title: Configurar o CUCM para Interoperação com Skype for Business Server
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumo: Configure o CUCM para trabalhar com Skype for Business Server.'
ms.openlocfilehash: 2e5e2cfc207fd9c4e52f7cd4da553dc756fddb4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863088"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar o CUCM para Interoperação com Skype for Business Server
 
**Resumo:** Configure o CUCM para trabalhar com Skype for Business Server.
  
> [!CAUTION]
> Esse recurso é testado com o Cisco Unified Communications Manager (CallManager ou CUCM) versão 10.5 usando apenas a configuração trunks sobre TCP. Verifique se o ambiente CUCM atende a esses critérios antes de prosseguir. 
  
As configurações descritas aqui são destinadas apenas como exemplos de como o CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou usos da funcionalidade CUCM alternativa também podem ser usados para obter o mesmo resultado. Nenhuma recomendação está implícita quanto à configuração ideal para um cenário específico.
  
Várias configurações de CUCM precisam ser confirmadas ou alteradas para interoperação com o VIS. Siga os procedimentos abaixo para evitar a falta das configurações necessárias.
  
### <a name="configure-the-cucm"></a>Configurar o CUCM

1. Faça logon no CUCM e navegue até Cisco Unified CM Administration - \> Roteamento de Chamadas- \> Classe de Controle- \> Partição.
    
2. Na tela Configuração de Partição, insira o nome e a descrição da partição e clique em **Adicionar Novo**.
    
3. Navegue até Cisco Unified CM Administration - \> Roteamento de Chamadas- \> Classe de Controle- \> Espaço de Pesquisa de Chamadas.
    
4. Na tela Configuração do Espaço de Pesquisa de Chamada, insira o nome do espaço de pesquisa de chamada e, em Partições Selecionadas, insira o nome da partição que você acabou de criar. Clique **em Salvar** quando terminar.
    
5. Navegue até Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile.
    
6. Na tela Configuração do Perfil de Segurança do Tronco SIP, de definir as opções de Informações de Perfil de Segurança do Tronco SIP, conforme mostrado, e clique em **Adicionar Novo**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de Segurança do Dispositivo  <br/> |Não Seguro  <br/> |
   |Tipo de Transporte de Entrada  <br/> |TCP + UDP  <br/> |
   |Tipo de Transporte de Saída  <br/> |TCP  <br/> |
   |Porta de entrada  <br/> |5060  <br/> |
   
7. Navegue até Cisco Unified CM Administration \> - Device- \> Device \> Configurações-SIP Profile.
    
8. Na tela Configuração de Perfil SIP, de definir as opções de Informações de Perfil SIP, conforme mostrado. 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrição  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Na mesma tela, role para baixo até a seção Informações de Perfil SDP. A opção Modificador de Largura de Banda no nível de sessão SDP para Oferta Antecipada e **Convites Re-convidados** é definida por padrão como TIAS e AS. Altere essa opção somente para TIAS. Se você deixar essa opção em sua configuração padrão, Skype for Business Server compreenderá as informações do modificador de largura de banda na mensagem SIP. TIAS significa Transport Independent Application Specific enquanto AS significa Application Specific. Estas são as opções SIP especificadas em RFC3890.
    
10. Na mesma tela, role para baixo ainda mais. Em Configuração Específica de Tronco  do Perfil SIP, selecione Suporte de Oferta Antecipada para chamadas de voz e vídeo e de definir-o como a opção Obrigatório **(inserir MTP, se** necessário). Isso permitirá que a CUCM configurar uma chamada SIP de saída com a Oferta Antecipada. Um novo recurso no CUCM 8.5 e além é que ele dá suporte à configuração de chamada de saída com a Oferta Antecipada sem exigir o Ponto de Terminação de Mídia (MTP).
    
11. Verifique se, na seção ping Opções SIP, a caixa é marcada ao lado de "Habilitar PING DE OPÇÕES para monitorar o status de destino para Troncos com Tipo de Serviço 'Nenhum (Padrão)'".
    
12. Quando terminar, clique em **Adicionar Novo**.
    
13. Navegue até Cisco Unified CM Administration- \> \> Device-Trunk. 
    
14. De definir o Protocolo de Dispositivo como SIP e pressione **Next**.
    
15. Em Informações do Dispositivo, de definir o Nome do Dispositivo e a Descrição (provavelmente para algo como SfBVideoInterop_SIPTrunk) e de definir a Lista de Grupo de Recursos de Mídia como um MRGL que contém os recursos de mídia corretos. 
    
16. Role para baixo mais adiante. O Ponto de Terminação de Mídia (MTP) não é necessário para Chamadas de Vídeo, se ainda não estiver desmarcado, desmarque-o. Verifique a opção Executar em todos os nós **cm unificados ativos.** Observe que você deve adicionar todos os nós CUCM à Skype for Business Server configuração.
    
17. Role para baixo mais adiante. De definir as opções Chamadas de Entrada e Configurações Desconectadas, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Chamando o espaço de pesquisa  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada do AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de Transformação de Partes Conectadas  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Role para baixo mais adiante. Na seção Destino das Informações SIP da configuração do Tronco SIP, especifique o FQDN do Pool do VIS ou o endereço IP de servidores VIS individuais no pool (adicionando várias entradas). Na Porta de Destino, especifique a Porta que o VIS está escutando para conexões do CUCM (o padrão é 6001). Especifique também o perfil de segurança do Tronco SIP e o perfil SIP que você criou anteriormente, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Perfil de Segurança de Tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Redirecionar o espaço de pesquisa de chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de pesquisa de chamada fora de caixa de diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Inscrever-se no espaço de pesquisa de chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de sinalização DTMF  <br/> |RFC 2833  <br/> |
   
19.  Role para baixo mais adiante. De definir as Informações de Gravação conforme apropriado para o seu sistema. Não há problema em deixá-lo definido como **Nenhum.** 
    
20. Quando terminar, clique em **Adicionar Novo**.
    
21. Navegue até Cisco Unified CM Administration - \> Roteamento de Chamadas- \> Roteamento de Rota/Busca- \> Padrão de Rota.
    
22. Na tela Configuração do Padrão de Rota, insira os parâmetros de definição de padrão mostrados abaixo. Role para baixo até a seção Transformações da Parte Chamada e desmarcar a máscara conforme mostrado e clique em **Adicionar Novo** quando terminar.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Padrão de rota  <br/> |7779999  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrição  <br/> |Partição para SfBVideoInterop  <br/> |
    |Lista de gateway/rota  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de Transformação da Parte Chamada  <br/> |+14257779999  <br/> |
   
23. Navegue até Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern.
    
24. Na tela Configuração do Padrão de Rota SIP, de definir as opções de Definição de Padrão, conforme mostrado, e clique em **Adicionar Novo**.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    | Uso do padrão <br/> |Roteamento de Domínio  <br/> |
    |Padrão IPv4  <br/> |contoso.com (deixe em branco se estiver usando IPv6)  <br/> |
    |Padrão IPv6  <br/> |contoso.com (deixe em branco se estiver usando IPv4)  <br/> |
    |Descrição  <br/> |Padrão SIPRoute para mediarv  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de tronco/rota SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Caixa de seleção Bloquear Padrão  <br/> |deixar desmarcado  <br/> |
   
25. Se você alterou as taxas de bits de áudio ou vídeo das configurações padrão, você precisará devolvê-las para os padrões. Para definir a taxa de bits para chamadas de Áudio/Vídeo, navegue até Cisco Unified CM Administration- \> System- \> Region Information- \> Region. Os padrões são mostrados abaixo para referência:
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Região  <br/> |Padrão  <br/> |
    |Lista de preferências de codec de áudio  <br/> |Padrão do sistema  <br/> |
    |Taxa máxima de bits de áudio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Taxa máxima de bits de sessão para chamadas de vídeo  <br/> |200000 kbps  <br/> |
    |Taxa máxima de bits de sessão  <br/> |2000000000 kbps  <br/> |
   
Neste ponto, o gateway de vídeo CUCM está configurado para funcionar com o VIS. A configuração correspondente precisará ser feita em cada VTC que você deseja integrar.
> [!NOTE]
> Para melhorar a resiliência, você pode configurar esse gateway CUCM para funcionar com um segundo Servidor de Interop de Vídeo ou pool vis. Consulte [Mecanismos de resiliência](../../plan-your-deployment/video-interop-server.md#resiliency) para obter mais informações.
  
## <a name="see-also"></a>Confira também

[Configurar um VTC para Interoperação com Skype for Business Server](configure-a-vtc-for-interoperation.md)
