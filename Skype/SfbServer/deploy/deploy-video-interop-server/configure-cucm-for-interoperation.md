---
title: Configurar CUCM para interoperação com Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumo: Configure CUCM para trabalhar com Skype para Business Server.'
ms.openlocfilehash: 6ace5eb2f6cb9763bf78b3930536ae50f8fee815
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986555"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar CUCM para interoperação com Skype para Business Server
 
**Resumo:** Configure CUCM para trabalhar com Skype para Business Server.
  
> [!CAUTION]
> Esse recurso é testado com Cisco Unified Communications Manager (CallManager ou CUCM) versão 10.5 usando troncos instalação somente sobre TCP. Verifique se o ambiente do CUCM atende a esses critérios antes de continuar. 
  
As configurações descritas aqui servem apenas como exemplos de como CUCM pode ser configurado para funcionar com um VIS. Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado. Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.
  
Várias configurações do CUCM precisam ser confirmadas ou alteradas para interoperação com o VIS. Siga os procedimentos abaixo para evitar que alguma configuração necessária fique faltando.
  
### <a name="configure-the-cucm"></a>Configurar o CUCM

1. Faça logon em CUCM e navegue para Cisco Unified CM administração -\>roteamento de chamada -\>classe de controle -\>partição.
    
2. Na tela Configuração de Partição, insira o nome e a descrição da partição e clique em **Adicionar Novo**.
    
3. Navegue até Cisco Unified CM administração -\>chamada roteamento -\>classe de controle -\>chamar o espaço de pesquisa.
    
4. Na tela Configuração do Espaço de Pesquisa de Chamada, insira o nome do espaço de pesquisa de chamada e, em Partições Selecionadas, insira o nome da partição que você acabou de criar. Clique em **Salvar** quando terminar.
    
5. Navegue até Cisco Unified CM administração -\>sistema -\>segurança -\>perfil de segurança de tronco SIP.
    
6. Na tela Configuração do Perfil de Segurança de Tronco SIP, defina as opções de Informações do Perfil de Segurança de Tronco SIP, conforme mostrado, e clique em **Adicionar Novo**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de Segurança do Dispositivo  <br/> |Não Seguro  <br/> |
   |Tipo de Transporte de Entrada  <br/> |TCP + UDP  <br/> |
   |Tipo de Transporte de Saída  <br/> |TCP  <br/> |
   |Porta de Entrada  <br/> |5060  <br/> |
   
7. Navegue até Cisco Unified CM administração -\>dispositivo -\>configurações do dispositivo -\>perfil SIP.
    
8. Na tela Configuração do Perfil SIP, define as opções de Informações do Perfil SIP, conforme mostrado. 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrição  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Na mesma tela, role até a seção de informações de perfil de SDP. Por padrão, a opção **Modificador de Largura de Banda de Nível de Sessão SDP para Early Offer e Re-invites** está definida como TIAS e AS. Altere-a para TIAS somente. Se você deixar essa opção em sua configuração padrão, Skype para Business Server não compreenderá as informações do modificador de largura de banda da mensagem SIP. TIAS significa Transport Independent Application Specific (Específico de Aplicativo Independente de Transporte) e AS significa Application Specific (Específico de Aplicativo). Essas são opções SIP especificadas na RFC3890.
    
10. Role a tela mais para baixo. Em configuração específica do tronco do perfil SIP, selecione **Inicial oferecer suporte a chamadas de voz e vídeos** e defini-la como a opção **obrigatório (insert MTP, se necessário)** . Isso permitirá que o CUCM configure uma chamada SIP de saída com Early Offer. Um novo recurso do CUCM 8.5 e acima é o suporte para a configuração de chamadas de saída com Early Offer sem a necessidade de um MTP (Ponto de Terminação de Mídia).
    
11. Verifique se, na seção de ping de Opções SIP, a caixa ao lado de "Ativar Ping de OPÇÕES para monitorar o status do destino de Troncos com o Tipo de Serviço 'Nenhum (Padrão)'" está marcada.
    
12. Quando terminar, clique em **Adicionar Novo**.
    
13. Navegue até Cisco Unified CM administração -\>dispositivo -\>tronco. 
    
14. Defina o Protocolo do Dispositivo como SIP e pressione **Avançar**.
    
15. Em Informações do Dispositivo, defina o Nome e a Descrição do Dispositivo (provavelmente algo como SfBVideoInterop_SIPTrunk) e a Lista de Grupos de Recursos de Mídia como um MRGL que contenha os recursos de mídia certos. 
    
16. Role a tela ainda mais para baixo. Como um MTP (Ponto de Terminação de Mídia) não é necessário para Chamadas de Vídeo, se essa opção ainda não estiver desmarcada, desmarque-a. Marque a opção para **Executar em todos os nós ativos do Unified CM**. Observe que você deve adicionar todos os nós CUCM para o Skype para configuração do servidor de negócios.
    
17. Role a tela ainda mais para baixo. Defina as opções de Chamadas de Entrada e Configurações de Partes Conectadas conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Espaço de Pesquisa de Chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de Transformação da Parte Conectada  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Role a tela ainda mais para baixo. Na seção destino SIP de informações da configuração do tronco SIP, especifique o FQDN de VIS do Pool ou o endereço IP de servidores de VIS individuais no pool (adição de várias entradas). Em Porta de Destino, especifique a porta de escuta do VIS para conexões do CUCM (o padrão é 6001). Além disso, especifique o perfil de segurança do Tronco SIP e o perfil SIP criados anteriormente, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Perfil de Segurança do Tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Reencaminhamento do Espaço de Pesquisa de Chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada de Referência Fora do Diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada SUBSCRIBE  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de Sinalização DTMF  <br/> |RFC 2833  <br/> |
   
19.  Role a tela ainda mais para baixo. Defina as Informações de Gravação conforme adequado para o seu sistema. Há problemas em deixá-lo definido como **None**. 
    
20. Quando terminar, clique em **Adicionar Novo**.
    
21. Navegue para Cisco Unified CM administração -\>roteamento de chamada -\>rota/busca-\>padrão da rota.
    
22. Na tela Configuração do Padrão de Rota, insira os parâmetros de definição de Padrão mostrados abaixo. Role a tela para baixo até a seção Transformações da Parte Chamada e defina a máscara conforme mostrado. Depois, clique em **Adicionar Novo** quando terminar.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Padrão de Rota  <br/> |7779999  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrição  <br/> |Partição de SfBVideoInterop  <br/> |
    |Lista de Gateways/Rotas  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de Transformação da Parte Chamada  <br/> |+14257779999  <br/> |
   
23. Navegue até Cisco Unified CM administração -\>chamada roteamento -\>padrão da rota de SIP.
    
24. Na tela Configuração do Padrão de Rota SIP, defina as opções de Definição de Padrão, conforme mostrado, e clique em **Adicionar Novo**.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    | Uso do Padrão <br/> |Roteamento de Domínio  <br/> |
    |Padrão IPv4  <br/> |contoso.com (deixe em branco se estiver usando IPv6)  <br/> |
    |Padrão IPv6  <br/> |contoso.com (deixe em branco se estiver usando IPv4)  <br/> |
    |Descrição  <br/> |Padrão SIPRoute para mediarv  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Lista de Troncos SIP/Rotas  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Caixa de seleção Padrão de Blocos  <br/> |deixe desmarcada  <br/> |
   
25. Se tiver alterado as configurações padrão de taxa de bits de vídeo ou áudio, você precisará retorná-las para os valores padrão. Para definir a taxa de bits para chamadas de áudio/vídeo, navegue para Cisco Unified CM administração -\>sistema -\>informações de região -\>região. Os valores padrão são mostrados abaixo como referência:
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Região  <br/> |Padrão  <br/> |
    |Lista de Preferências de Codec de Áudio  <br/> |Padrão do Sistema  <br/> |
    |Taxa Máxima de Bits de Áudio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Taxa Máxima de Bits da Sessão para Chamadas de Vídeo  <br/> |200000 kbps  <br/> |
    |Taxa Máxima de Bits da Sessão  <br/> |2000000000 kbps  <br/> |
   
Agora, o gateway de vídeo do CUCM está configurado para funcionar com o VIS. Você precisará fazer uma configuração correspondente em cada VTC que desejar integrar.
> [!NOTE]
> Para melhorar a resiliência, convém configurar esse gateway CUCM para trabalhar com um pool de servidor de interoperabilidade de vídeo ou VIS segundo. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para obter mais informações.
  
## <a name="see-also"></a>Consulte também

[Configurar um VTC para interoperação com Skype para Business Server](configure-a-vtc-for-interoperation.md)