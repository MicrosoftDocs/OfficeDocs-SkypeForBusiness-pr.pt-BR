---
title: Configurar o CUCM para interoperação com o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Resumo: Configure o CUCM para trabalhar com o Skype for Business Server.'
ms.openlocfilehash: b0087e54b91b8c11bfcaba0c1eb732183db252bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302787"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurar o CUCM para interoperação com o Skype for Business Server
 
**Resumo:** Configure o CUCM para trabalhar com o Skype for Business Server.
  
> [!CAUTION]
> Essa funcionalidade é testada com o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM) versão 10,5 usando a configuração de troncos somente via TCP. Verifique se o ambiente do CUCM atende a esses critérios antes de continuar. 
  
As configurações descritas aqui servem apenas como exemplos de como o CUCM pode ser configurado para trabalhar com um VIS. Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado. Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.
  
Várias configurações do CUCM precisam ser confirmadas ou alteradas para interoperação com o VIS. Siga os procedimentos abaixo para evitar que alguma configuração necessária fique faltando.
  
### <a name="configure-the-cucm"></a>Configurar o CUCM

1. Conecte-se ao CUCM e navegue até a Cisco Unified\>cm Administration-\>Class Routing-Class\>of Control-Partition.
    
2. Na tela Configuração de Partição, insira o nome e a descrição da partição e clique em **Adicionar Novo**.
    
3. Navegue até Administração unificada de\>administração do Gerenciador\>de chamadas-classe\>de roteamento de chamadas de controle de chamada de controle.
    
4. Na tela Configuração do Espaço de Pesquisa de Chamada, insira o nome do espaço de pesquisa de chamada e, em Partições Selecionadas, insira o nome da partição que você acabou de criar. Clique em **Salvar** quando terminar.
    
5. Navegue até o perfil de segurança do\>tronco do\>Cisco Unified Administration-System-Security-\>SIP Trunk.
    
6. Na tela Configuração do Perfil de Segurança de Tronco SIP, defina as opções de Informações do Perfil de Segurança de Tronco SIP, conforme mostrado, e clique em **Adicionar Novo**.
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modo de Segurança do Dispositivo  <br/> |Não Seguro  <br/> |
   |Tipo de Transporte de Entrada  <br/> |TCP + UDP  <br/> |
   |Tipo de Transporte de Saída  <br/> |TCP  <br/> |
   |Porta de Entrada  <br/> |5060  <br/> |
   
7. Navegue até Administração de CM unificado do Cisco-\>dispositivo-\>configurações de dispositivo-\>perfil SIP.
    
8. Na tela Configuração do Perfil SIP, define as opções de Informações do Perfil SIP, conforme mostrado. 
    
   |**Parâmetro**|**Configuração recomendada**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrição  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Na mesma tela, role para baixo até a seção informações do perfil SDP. Por padrão, a opção **Modificador de Largura de Banda de Nível de Sessão SDP para Early Offer e Re-invites** está definida como TIAS e AS. Altere-a para TIAS somente. Se você deixar esta opção em sua configuração padrão, o Skype for Business Server não entenderá as informações do modificador de largura de banda na mensagem SIP. TIAS significa Transport Independent Application Specific (Específico de Aplicativo Independente de Transporte) e AS significa Application Specific (Específico de Aplicativo). Essas são opções SIP especificadas na RFC3890.
    
10. Role a tela mais para baixo. Na configuração específica do tronco do perfil SIP, selecione a **oferta antecipada para chamadas de voz e vídeo** e defina-a como a opção **obrigatório (inserir MTP, se necessário)** . Isso permitirá que o CUCM configure uma chamada SIP de saída com Early Offer. Um novo recurso do CUCM 8.5 e acima é o suporte para a configuração de chamadas de saída com Early Offer sem a necessidade de um MTP (Ponto de Terminação de Mídia).
    
11. Verifique se, na seção de ping de Opções SIP, a caixa ao lado de "Ativar Ping de OPÇÕES para monitorar o status do destino de Troncos com o Tipo de Serviço 'Nenhum (Padrão)'" está marcada.
    
12. Quando terminar, clique em **Adicionar Novo**.
    
13. Navegue até a administração do dispositivo de\>administração unificada da Cisco-\>trunk Device. 
    
14. Defina o Protocolo do Dispositivo como SIP e pressione **Avançar**.
    
15. Em Informações do Dispositivo, defina o Nome e a Descrição do Dispositivo (provavelmente algo como SfBVideoInterop_SIPTrunk) e a Lista de Grupos de Recursos de Mídia como um MRGL que contenha os recursos de mídia certos. 
    
16. Role a tela ainda mais para baixo. Como um MTP (Ponto de Terminação de Mídia) não é necessário para Chamadas de Vídeo, se essa opção ainda não estiver desmarcada, desmarque-a. Marque a opção para **Executar em todos os nós ativos do Unified CM**. Observe que você deve adicionar todos os nós do CUCM à configuração do Skype for Business Server.
    
17. Role a tela ainda mais para baixo. Defina as opções de Chamadas de Entrada e Configurações de Partes Conectadas conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Espaço de Pesquisa de Chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS de Transformação da Parte Conectada  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Role a tela ainda mais para baixo. Na seção destino de informações SIP da configuração do tronco SIP, especifique o FQDN do pool de VIS ou o endereço IP de servidores individuais do VIS no pool (adicionando várias entradas). Em Porta de Destino, especifique a porta de escuta do VIS para conexões do CUCM (o padrão é 6001). Além disso, especifique o perfil de segurança do Tronco SIP e o perfil SIP criados anteriormente, conforme mostrado.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Perfil de Segurança do Tronco SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Reencaminhamento do Espaço de Pesquisa de Chamada  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada de Referência Fora do Diálogo  <br/> |CSS_SfBVideoInterop  <br/> |
    |Espaço de Pesquisa de Chamada SUBSCRIBE  <br/> |CSS_SfBVideoInterop  <br/> |
    |Perfil SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Método de Sinalização DTMF  <br/> |RFC 2833  <br/> |
   
19.  Role a tela ainda mais para baixo. Defina as Informações de Gravação conforme adequado para o seu sistema. É bom deixá-lo definido como **None**. 
    
20. Quando terminar, clique em **Adicionar Novo**.
    
21. Navegue até o padrão Cisco Unified\>cm Administration-\>Routing Route-Route\>/rota de busca.
    
22. Na tela Configuração do Padrão de Rota, insira os parâmetros de definição de Padrão mostrados abaixo. Role a tela para baixo até a seção Transformações da Parte Chamada e defina a máscara conforme mostrado. Depois, clique em **Adicionar Novo** quando terminar.
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Padrão de Rota  <br/> |7779999  <br/> |
    |Partição de Rota  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrição  <br/> |Partição de SfBVideoInterop  <br/> |
    |Lista de Gateways/Rotas  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Máscara de Transformação da Parte Chamada  <br/> |+14257779999  <br/> |
   
23. Navegue até o padrão Cisco Unified\>cm Administration-\>Routing Route-SIP Route.
    
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
   
25. Se tiver alterado as configurações padrão de taxa de bits de vídeo ou áudio, você precisará retorná-las para os valores padrão. Para definir a taxa de bits para chamadas de áudio/vídeo, navegue até informações\>\>\>de região unificada de administração do Cisco-região. Os valores padrão são mostrados abaixo como referência:
    
    |**Parâmetro**|**Configuração recomendada**|
    |:-----|:-----|
    |Região  <br/> |Padrão  <br/> |
    |Lista de Preferências de Codec de Áudio  <br/> |Padrão do Sistema  <br/> |
    |Taxa Máxima de Bits de Áudio  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Taxa Máxima de Bits da Sessão para Chamadas de Vídeo  <br/> |200000 kbps  <br/> |
    |Taxa Máxima de Bits da Sessão  <br/> |2000000000 kbps  <br/> |
   
Agora, o gateway de vídeo do CUCM está configurado para funcionar com o VIS. Você precisará fazer uma configuração correspondente em cada VTC que desejar integrar.
> [!NOTE]
> Para melhorar a resiliência, talvez você queira configurar esse CUCM gateway para funcionar com um segundo servidor de interoperabilidade de vídeo ou pool VIS. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para obter mais informações.
  
## <a name="see-also"></a>Confira também

[Configurar um VTC para interoperação com o Skype for Business Server](configure-a-vtc-for-interoperation.md)
