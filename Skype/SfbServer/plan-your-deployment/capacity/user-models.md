---
title: Modelos de usuário em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: Os modelos de usuário descritos aqui fornecem a base para as medições e recomendações de planejamento de capacidade descritas em Uso do modelo de usuário de planejamento de capacidade para Skype for Business Server.
ms.openlocfilehash: e72a16668c0247a23ac4d032e0a3f09b06a71cc5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768629"
---
# <a name="user-models-in-skype-for-business-server"></a>Modelos de usuário em Skype for Business Server
 
Os modelos de usuário descritos aqui fornecem a base para as medições e recomendações de planejamento de capacidade descritas em Uso do modelo de usuário de planejamento de capacidade para [Skype for Business Server](user-model.md).
  
## <a name="skype-for-business-server-user-models"></a>Skype for Business Server Modelos de usuário

A tabela a seguir descreve o modelo de usuário para registro, contatos, mensagens instantâneas (IM) e presença para Skype for Business Server.
  
**Modelo de usuário de ambiente e registro**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Tamanho da implantação e distribuição  <br/> |Modelamos uma grande implantação com três locais centrais, com um pool de Front-end por local.  <br/> |
|Porcentagem de usuários do Active Directory  <br/> |Presumimos que 70% de todos os usuários do Active Directory na organização estão habilitados para Skype for Business Server. 80% desses usuários habilitados estão conectados Skype for Business Server dia (80% de responsabilidade). Os usuários simultâneos são a base para os números no restante desta seção.  <br/> |
|Mudanças do Active Directory  <br/> |Presumimos que 0,5% do total de usuários são criados e habilitados para o Skype for Business no Active Directory a cada semana e que 0,5% do total de usuários são desabilitados do Active Directory e Skype for Business todas as semanas. 5% dos usuários possuem pelo menos um atributo do Active Directory alterado cada semana.  <br/> |
|Grupos de distribuição do Active Directory  <br/> |Supomos que o número de grupos de distribuição do Active Directory na organização seja igual a três vezes o número de todos os usuários no Active Directory. Os grupos de distribuição têm os seguintes tamanhos:  <br/> • 64% têm de 2 a 30 usuários  <br/> • 13% têm de 31 a 50 usuários  <br/> • 10% têm de 51 a 100 usuários  <br/> • 13% têm de 101 a 500 usuários  <br/> |
|Usuários de VoIP (Voz sobre IP)  <br/> |60% dos usuários Skype for Business Server estão habilitados para comunicações unificadas (ou seja, seus números de telefone são de propriedade Skype for Business Server).  <br/> |
|Distribuição dos cliente registrados  <br/> |65% dos clientes são executados Skype for Business software, incluindo o Skype for Business e o Lync Telefone Edition.  <br/> 30% dos clientes executando software cliente de uma versão anterior do Lync.  <br/> 5% dos clientes que usam Skype for Business Web App.  <br/> Se a mobilidade estiver habilitada, presumimos que 40% dos usuários estão usando a mobilidade simultaneamente com as outras opções de cliente registradas anteriormente. Nesse caso, a taxa de MPOP (múltiplos pontos de presença) do cliente é 1:1.9. Se a mobilidade está desabilitada, a taxa MPOP é de 1:1.5.  <br/> |
|Distribuição dos usuários remotos  <br/> |70% os usuários se conectam internamente.  <br/> 30% dos usuários se conectam por meio de um Servidor de Borda (você também pode opcionalmente ter um Diretor aqui, mas não é necessário).  <br/> |
|Distribuição dos contatos  <br/> |O número máximo de contatos de um usuário é 1.000. Menos de um 1% dos usuários tem 1.000 contatos. Menos de 25% dos usuários têm 100 ou mais contatos.  <br/> Média de 80 contatos para usuários com conectividade pública na nuvem. Desses usuários:  <br/> • 50% dos contatos estão dentro da organização. 10% desses usuários são usuários remotos, se conectando de fora do firewall.  <br/> • 40% dos contatos são Skype usuários.  <br/> • 10% dos contatos são de parceiros federados.  <br/> Média de 50 contatos para usuários sem conectividade pública na nuvem. Desses usuários:  <br/> • 80% dos contatos estão dentro da organização. 10% desses usuários são usuários remotos, se conectando de fora do firewall.  <br/> • 20% dos contatos são de parceiros federados.  <br/> Cada usuário possui 1 grupo de distribuição em sua lista de contatos. Para testar o desempenho, assumimos que os grupos de distribuição são sempre expandidos.  <br/> |
|Tempo de sessão  <br/> |A sessão média de logon do usuário dura 12 horas. Todos os usuários fazem logon em até 120 minutos após o início da sessão.  <br/> |
   
**Modelo de usuário de IM e presença**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Sessões de IM ponto a ponto  <br/> |Cada usuário tem em média seis sessões de IM ponto a ponto por dia.  <br/> 10 mensagens instantâneas por sessão.  <br/> Cada mensagem é corresponder a duas mensagens SIP INFO e 2 mensagens SIP 200 OK (para os indicadores de status, como " \<Name\> está Digitando")  <br/> |
|Sessões de IM de grupo  <br/> |O número médio de mensagens enviadas em uma sessão somente IM de grupo é 5 por usuário.  <br/> O número médio de mensagens enviadas na parte de mensagens IM de uma conferência AV é 2 por usuário.  <br/> |
|Sondagem de presença  <br/> |Em geral, supomos o pool de presença com uma média de 60 pools por usuário, por hora. Para cada usuário, suponha uma média de:  <br/> • Uma sondagem por dia da presença de usuários na guia organização do usuário (mas não na lista contatos). O número médio de não contatos na guia organização do usuário é de 15 usuários. Dois cartões de visita visualizando operações por dia.  <br/> • Uma sondagem de presença sempre que o usuário clica em outro usuário para iniciar uma conversa, estimada de uma vez por hora.  <br/> • Seis pesquisas de usuário por hora. Cada vez que uma pesquisa é realizada, um pool de lote é enviado para todos na lista de resultados da pesquisa. Suponha que o tamanho médio dos resultados da pesquisa é 20. Se os resultados da pesquisa permanecem na tela, o pool de lote é atualizado a cada 5 minutos; assumimos que haverá duas atualizações por hora.  <br/> • Quando o usuário abre ou visualiza um email no Outlook, uma sondagem sobre a presença de usuários nos campos Para: e CC: do email, estimado em cinco emails por hora e quatro usuários por email.  <br/> |
|Assinaturas de presença  <br/> |Quando um usuário adiciona outro como contato, o primeiro usuário está se inscrevendo em cinco categorias de informação sobre o segundo usuário. As atualizações dessas categorias de informação são automaticamente enviadas ao primeiro usuário. <br/> Para cada cliente, uma única solicitação de inscrição em lote é enviada para obter o estado de presença em uma média de 40 contatos, com 40 diálogos adicionais para obter presença de contatos federados.  <br/> A presença de membros de um grupo de distribuição expandido é encontrada através de inscrições de presença persistente, não pool, e é modelada como 1 expansão por usuário para cada 2 horas.  <br/> Assinaturas curtas ocorrem quando um usuário faz login, há uma assinatura em lote para todos os contatos do usuário e, em seguida, o usuário logo faz logo off. Assumimos 6 inscrições curtas por usuário, por hora, onde cada inscrição dura 10 minutos. <br/> |
|Publicação de Presença  <br/> |O estado de presença é publicado em uma média de 4 publicações por usuário, por hora, com um máximo de 6 por usuário, por hora.  <br/> |
|Tamanho do Documento de Presença  <br/> |O tamanho médio de um documento de presença completo é assumido como 4K, com um máximo de 25K.  <br/> |
   
A tabela a seguir descreve o modelo de usuário para uso do catálogo de endereços.
  
**Modelo de usuário para uso do catálogo de endereços**

|**Modo de pesquisa do Catálogo de endereços**|**Uso**|
|:-----|:-----|
|Consulta da web do Catálogo de endereços somente (todas as consultas realizadas pelo serviço Consulta da web do Catálogo de endereços)  <br/> |Quatro consultas de prefixo por usuário, por dia.  <br/> 60 consultas de pesquisa exatas por usuário, por dia. 40% delas são em lote, com uma média de 20 contatos por consulta. Os outros 60% das consultas servem para um único contato.  <br/> 25 consultas de foto por usuário, por dia. 24 para uma única foto, o restante é uma consulta em lote com uma média de 20 contatos.  <br/> Uma consulta de pesquisa de organização por usuário, por dia.  <br/> |
|Modo misto, arquivo do catálogo de endereços e consultas da web usadas. Esse é o modo padrão.  <br/> |Somente dois tipos de consulta vão para a rede, as consultas de pesquisa de foto e organizacional total.  <br/> 25 consultas de foto por usuário, por dia. 24 para uma única foto, o restante é uma consulta em lote com uma média de 20 contatos.  <br/> Uma consulta de pesquisa de organização por usuário, por dia.  <br/> |
   
A tabela a seguir descreve o modelo de conferência.
  
**Modelo de conferência**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Reuniões agendadas versus reuniões do tipo "Reunir Agora"  <br/> |60% agendadas, 40% não agendadas.  <br/> Das reuniões agendadas, presumimos que 80% sejam atribuídas a conferências, que são ocorrências de conferências recorrentes; 10% são reuniões abertas única; 8% são reuniões anônimas única e 2% são reuniões fechadas única.  <br/> |
|Distribuição de cliente de conferência  <br/> |Para reuniões agendadas:  <br/> • 65% dos usuários de conferência usam Skype for Business 2016.  <br/> • 5% dos usuários de conferência usam Skype for Business Web App.  <br/> • 30% dos usuários de conferência usam clientes anteriores, incluindo o Lync 2013 e o Microsoft Lync 2010.  <br/> Para reuniões não agendadas:  <br/> • 70% dos usuários de conferência usam Skype for Business.  <br/> • 30% dos usuários de conferência usam clientes anteriores, incluindo o Lync 2013 e o Microsoft Lync 2010.  <br/> |
|Simultaneidade de reunião  <br/> |5% dos usuários estarão em conferências durante as horas de trabalho. Dessa forma, em um pool de 80.000 usuários, 4.000 usuários poderão estar em conferências a qualquer momento.  <br/> |
|Distribuição do áudio de reunião  <br/> |40% de combinação entre conferência de áudio VoIP e discada, com uma proporção de 3:1 de usuários VoIP para usuários discados.  <br/> 35% somente de áudio VoIP.  <br/> 15% somente de áudio de conferência discada.  <br/> 10% sem áudio (conferências somente de IM, com uma média de cinco mensagens enviadas por usuário).  <br/> |
|Combinação de mídias para conferências  <br/> |75% das conferências são conferências da Web, com áudio mais alguma outra modalidade de colaboração.  <br/> Para essas conferências, os outros métodos de colaboração são os seguintes:  <br/> **Observação:** Esses números somam mais de 100% porque uma conferência pode ter vários métodos de colaboração. <br/> • 50% adicionar compartilhamento de aplicativos. Assumimos que um usuário envia dados a um pico de 1,1 MB por segundo.  <br/> • 50% adicionam mensagens instantâneas (com uma média de 2 mensagens por usuário).  <br/> • 20% adicionam colaboração de dados, incluindo PowerPoint ou quadro de PowerPoint Nesses, uma média de 2 arquivos PowerPoint apresentados por conferência, com um tamanho médio de arquivo PowerPoint de 10 MB (sem vídeo incorporado) ou 30 MB (com vídeo incorporado). Média de 20 anotações por quadro de anotações.  <br/> • 20% adicionar vídeo. Destes usuários, 70% estão em conferências habilitadas para vídeo multivisualização, onde cada usuário recebe 2-3 fluxos de vídeo.  <br/> • 15% adicione anotações compartilhadas.  <br/> |
|Distribuição dos participantes da reunião  <br/> |50% de usuários internos autenticados.  <br/> 25% de usuários de acesso remoto autenticados.  <br/> 15% de usuários anônimos.  <br/> 10% de usuários federados.  <br/> |
|Distribuição de ingresso na reunião  <br/> |Os usuários são simulados como participação da reunião dentro dos primeiros 5 minutos.  <br/> |
   
Em pools de Front-End regulares, Skype for Business Server tem um tamanho máximo de reunião suportado de 250 usuários. Cada pool pode hospedar uma reunião de 250 usuários por vez. Enquanto esta grande reunião está ocorrendo, o pool também pode hospedar outras conferências menores. Além disso, é possível suportar reuniões de até 1000 usuários configurando um pool exclusivo para hospedar estas reuniões. Para obter detalhes, [consulte Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Conferências foram simuladas como a seguir:
  
- 85% das conferências tinham quatro participantes.
    
- 10% das conferências tinham seis participantes.
    
- 5% das conferências tinham 11 participantes.
    
- Uma grande conferência de 250 usuários.
    
A tabela a seguir fornece detalhes sobre o modelo de usuário para conferências envolvendo usuários discados.
  
**Modelo de usuário de conferência discada**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Autenticado/anônimo  <br/> |70% de chamadores participaram como anônimos e foram solicitados por um nome de registro. 30% participaram como usuários autenticados.  <br/> |
|Duração da chamada e música em espera  <br/> |A duração média da chamada sem música em espera: 50 segundos.  <br/> 50% dos usuários de chamada recebida ouvem música em espera, durante uma média de 5 minutos.  <br/> |
|DTMF (Dual-tone multifrequency)  <br/> |15% das conferências somente discadas têm líderes de telefone. 10% das conferências mistas que incluem usuários discados também têm líderes de telefone.  <br/> 20% dos líderes de telefone usam 2 comandos DTMF por conferência.  <br/> |
|Idiomas do anúncio  <br/> |As simulações usam Inglês como o idioma de anúncio.  <br/> |
   
A tabela a seguir fornece detalhes sobre o modelo de usuário para lobbies de conferência.
  
**Modelo de usuário de lobby de conferência**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Número de usuários no lobby  <br/> |5% dos usuários discados passam pelo lobby e 25% dos outros usuários passam pelo lobby  <br/> |
|Admissão a partir do lobby  <br/> |Em simulações, todos os usuários foram admitidos pelo apresentador antes do tempo limite do cliente.  <br/> |
   
A tabela a seguir descreve o modelo de usuário para outras sessões ponto a ponto.
  
**Modelo de usuário de sessões ponto a ponto**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Compartilhamento de aplicativos  <br/> |Cada usuário participa de 5 sessões de compartilhamento de aplicativo ponto a ponto por mês, uma média de 0,25 sessões por dia.  <br/> |
|Transferência de arquivo  <br/> |Cada usuário participa de uma sessão de transferência de arquivo ponto a ponto por mês (como parte de uma sessão de IM), para uma média de 0,05 sessões por dia. O tamanho de arquivo médio da sessão transferido é de 1 MB.  <br/> |
   
A tabela a seguir descreve o modelo de usuário para políticas.
  
**Políticas de Modelo do Usuário**

|**Categoria**|**Descrição**|
|:-----|:-----|
|Políticas de Arquiamento, Presença e Conferência  <br/> |Assumimos que há uma política global, 10 políticas de conferência de marcação, 4 políticas de Arquivamento e 10 políticas de presença de tag.  <br/> |
|Política de voz  <br/> |Assumimos que há uma política global e 2 políticas de tag por local. 100% dos locais possuem uma política local e 30% dos usuários possuem uma política por usuário atribuída. Assumimos um plano de discagem por local e duas rotas por local.  <br/> |
   
## <a name="busy-hour"></a>Horário de pico

Para sessões ponto a ponto, a carga durante o pico é calculada usando tentativas de chamada no horário de pico (BHCA). Esse termo do setor de voz supõe que 50% de todas as chamadas para esse dia serão completadas em 20% do tempo. Isso é calculado usando a seguinte fórmula:
  
 `BHCA=(total calls * 0.5) / 1.6`
  
O teste de desempenho simulou o horário de pico executando sessões VoIP e outras sessões ponto a ponto com uma carga de hora de pico durante pelo menos 1,6 hora por dia.
  
A carga de pico de conferência supõe que 75% de todas as conferências para um dia de oito horas ocorre em 4 horários de pico. Esses horários de pico têm 1,5 vezes a carga média de conferência.
  
## <a name="enterprise-voice-to-pstn-calls"></a>Enterprise Voice chamadas PSTN

As seguintes suposições se aplicam a Enterprise Voice chamadas:
  
- 60% dos usuários estão habilitados para Enterprise Voice e 60% desses usuários estão habilitados para chamada PSTN.
    
- Cada um destes usuários habilitados para chamada PSTN faz 4 chamadas PSTN durante a hora ocupada. Cada duração de chamada é de 3 minutos.
    
- 65% destas chamadas de voz PSTN usam bypass de mídia.
    
## <a name="mobility"></a>Mobilidade

40% dos usuários registrados são assumidos como habilitados para Mobilidade. Para cada usuário que possui habilidade habilitado, assumimos que a atividade do cliente móvel é aditivo àquelas de outras instâncias MPOP deste usuário, com exceção das interações de conferência, para as quais o cliente de mobilidade é apenas outro tipo de cliente que pode ser usado para participar de conferências.
  
## <a name="persistent-chat"></a>Chat Persistente

Assumimos que 25% dos usuários registrados sejam envolvidos em sessões de chat Persistente, com as seguintes características:
  
- Uma média de 1,5 salas de bate-papo por usuário
    
- Cada sala de bate-papo resulta em 12 solicitações de pool por hora, indicando uma média de 10 usuários cada
    
## <a name="response-group-and-call-park"></a>Grupo de Resposta e Estacionamento de Chamadas

Assumimos que 0,15% dos usuários registrados pertencem aos grupos de resposta. Assumimos que 0,02% dos usuários registrados possuem chamadas estacionadas em um determinado ponto do tempo.
  

