---
title: Usar o painel de controle de qualidade de chamada para Skype para o servidor de negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Resumo: Saiba mais sobre como usar o painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 6b431bb34ca6350662fbae720c61d2033d95fba4
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533424"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usar o painel de controle de qualidade de chamada para Skype para o servidor de negócios
 
**Resumo:** Saiba mais sobre como usar o painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
O CQD permite que os profissionais de TI utilizem dados agregados para identificar áreas de foco em seu ambiente com problemas de qualidade de mídia. Ele permite que um profissional de TI compare estatísticas de diferentes grupos de usuários e identifique tendências e padrões. O foco não está em resolver problemas de chamadas individuais, mas em identificar problemas e soluções que se apliquem a muitos usuários em um determinado ambiente.
  
## <a name="call-quality-dashboard-user-guide"></a>Guia do Usuário do Painel de Qualidade da Chamada

O Painel de Qualidade da Chamada (CQD) é um portal da Web para criar e organizar rapidamente relatórios baseados em dados de qualidade da experiência (QoE). O CQD implanta um cubo SSAS para agregar os dados no banco de dados de Métricas de QoE. Isso possibilita aos usuários criar e modificar relatórios e fazer investigações em tempo real. Embora seja possível usar o Excel para se conectar diretamente ao cubo, o portal é otimizado para diversos fluxos de trabalho que envolvem dados de QoE. Esses dados incluem o armazenamento em cache de dados de relatório para acesso rápido, links profundos para relatar páginas para compartilhamento e publicação de informações, edição e criação simplificadas de relatórios, e metadados editáveis ​​para descrições de relatórios. Além disso, o CQD expõe APIs da Web que dão aos usuários acesso programático aos dados do cubo para uso em painéis personalizados.  
  
### <a name="feature-overview"></a>Visão geral do recurso

Quando o usuário visitar o Painel de Qualidade da Chamada, ele verá o seguinte:
  
![Usar CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. O painel de resumo"" é onde o contexto para "Relatório definir" (à direita) pode ser encontrado. 
    
2. Propriedades de nível de conjunto do relatório (incluindo a altura do eixo y) podem ser definidas clicando em "Editar" no painel Resumo.
    
3. A Trilha ajuda os usuários a identificar sua localização atual na hierarquia do conjunto de relatórios.  
    
4. Os relatórios com sub-relatórios são mostrados com um link azul. Clicar no link fará uma busca detalhada nos relatórios filho.  
    
Mover o mouse sobre os gráficos de barras e as linhas de tendência mostrará valores detalhados. O relatório que tem o foco mostrará no menu Ação: "Editar", "Clone", "Excluir" e "Download". 
  
### <a name="default-reports"></a>Relatórios Padrão

Quando o usuário acessa o portal do Painel de Qualidade da Chamada pela primeira vez, um conjunto padrão de relatórios é criado automaticamente. Esses relatórios são, por vezes, chamados de relatórios do sistema. O usuário pode modificar ou excluir esses relatórios livremente. Geralmente, os usuários os estenderão criando novos relatórios irmão ou filho.  
  
No nível superior, o relatório de "Áudio fluxos mensal tendência" mostra a tendência mensal para todos os fluxos de áudio. Mova o mouse sobre as barras de um gráfico de barras para mostrar uma visão mais detalhada dos dados representados pelo gráfico de barras. Clicando no título do relatório de tendência mensal de fluxos de áudio navegarão ao relatório "Gerenciada versus fluxos de áudio não gerenciado", onde os relatórios são divididos entre Managed e chamadas não gerenciadas. As chamadas gerenciadas são aquelas feitas de dentro do firewall corporativo por conexões com fio. As chamadas não gerenciadas incluem chamadas feitas de fora do firewall corporativo, bem como todas as chamadas feitas por Wi-Fi.
  
O outro relatório de nível superior é chamado "Usuário informou chamada qualidade classificação histograma." As Classificações de Qualidade da Chamada são os números fornecidos pelos usuários do Skype for Business no final de uma chamada para indicar a qualidade da chamada. Os números de classificação variam de 1 a 5, sendo 1 o pior e 5, o melhor. O histograma mostra o número de chamadas de áudio que tiveram a classificação indicada em um mês. 
  
Em geral, com um clique no título dos relatórios você navega até eles com filtros adicionais sobre os dados. Nos relatórios do sistema, cada relatório filho exibe um subconjunto dos dados disponíveis em seu relatório pai. Isso fornece um modelo conceitualmente simples para a resolução de problemas: diminuir o espaço do problema, investigando em qual sub-relatório os dados problemáticos ou a tendência estão confinados. A capacidade de criar novos sub-relatórios permite que os usuários investiguem suas próprias hipóteses quanto à proveniência das tendências de dados específicos.
  
### <a name="creating-and-editing-reports"></a>Criar e editar relatórios

Quando você clica em "Editar" no menu Ação, de um relatório, os usuários verão o Editor de relatório. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de Relatório é uma interface do usuário para editar essas consultas, bem como as opções de exibição do relatório. Quando um usuário abrir o Editor de Relatório, verá o seguinte:
  
![Usar CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. Dimensões, medidas e filtros são escolhidos no painel esquerdo. Passar o mouse sobre um dos valores existentes mostrará um botão "x" que permite que o valor a ser removido. Clicar no botão "plus" ao lado de um título abrirá a caixa de diálogo para adicionar uma nova dimensão, medida ou filtro. 
    
2. As opções para a personalização de gráficos são exibidas na parte superior.
    
3. Uma visualização do relatório está disponível no Editor de Relatório.  
    
4. Uma descrição detalhada do relatório pode ser criada usando a caixa de edição na parte inferior.  
    
### <a name="sparklines-in-tables"></a>Minigráficos em tabelas

Quando StartDate.Month é adicionado como uma dimensão e os dados são processados como tendência na forma de tabela, gráficos de barras e minigráficos podem ser mostrados dentro das células da tabela. Mova o ponteiro do mouse sobre o gráfico de barras e os minigráficos mostrarão os valores dos meses individuais.  
  
![Usar CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
Em ordem para os gráficos de barras e os Minigráficos apareça, a caixa de seleção "Mostrar minigráficos" na parte superior do Editor de relatório deve ser verificada. Isso selecionará a opção Tendência e moverá Mês para a última dimensão, o que também pode ser feito clicando em Mês e usando as setas para cima e para baixo para deslocar StartDate.Month para cima ou para baixo. 
  
### <a name="settings"></a>Configurações

Localizado no canto superior direito do painel, o menu de configurações contém links para páginas úteis, como as páginas Integridade do Sistema e Sobre.
  
![Usar CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
Se ou não exibir descrições e carimbos de data / hora em que é até usuários individuais, e essas configurações afetam apenas a versão do indivíduo do painel de controle, não modifique o relatório definido ou veem quais outros usuários. Ao limpar o cache, todas as consultas recarregam seus dados do cubo, enquanto que a restauração dos padrões exclui todos os relatórios criados ou modificados pelo usuário e recria o conjunto de relatórios do sistema – o que o usuário veria ao fazer logon pela primeira vez.
  
O Link do Painel de Usuários mostra uma página onde os usuários podem visualizar outros usuários do CQD e navegar em seus relatórios. Ao compartilhar um conjunto de relatórios, basta copiar o link na barra de URL e compartilhá-lo com outro usuário do CQD. Este link será o mesmo como um outros usuários veria na página Link de painel usuários sob o nome do usuário.
  
### <a name="supplying-subnet-information"></a>Fornecer informações da sub-rede

Dados adicionais podem ser revelados se informações específicas do site forem inseridas no banco de dados de Arquivo para fornecer informações de mapeamento de sub-rede para edifício (por exemplo, a qualidade da chamada com/sem fio por edifício).  
  
No mínimo, as seguintes tabelas precisam ser preenchidas para criar estes relatórios:
  
- CqdBuilding
    
- CqdNetwork
    
Informações adicionais podem ser fornecidas nas tabelas CqdBuildingType e CqdBuildingOwnershipType para permitir mais filtragem e busca detalhada.  
  
Os esquemas dessas tabelas são definidos da seguinte forma:
  
**CqdBuilding**

|**Coluna**|**Tipo de dados**|**Permitir Nulos?**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|BuildingKey  <br/> |int  <br/> |Não  <br/> |Chave primária da tabela CqdBuilding.  <br/> |
|BuildingName  <br/> |varchar(80)  <br/> |Não  <br/> |Nome do edifício.  <br/> |
|BuildingShortName  <br/> |varchar(10)  <br/> |Não  <br/> |Versão abreviada do nome do edifício.  <br/> |
|OwnershipTypeId  <br/> |int  <br/> |Não  <br/> |Chave estrangeira que deve corresponder a uma das entradas da tabela CqdBuildingOwners.  <br/> |
|BuildingTypeId  <br/> |int  <br/> |Não  <br/> |Chave estrangeira que deve corresponder à que consta nas entradas da tabela CqdBuildingType.  <br/> |
|Latitude  <br/> |float  <br/> |Sim  <br/> |Latitude do edifício.  <br/> |
|Longitude  <br/> |float  <br/> |Sim  <br/> |Longitude do edifício.  <br/> |
|CityName  <br/> |varchar(30)  <br/> |Sim  <br/> |Nome da cidade onde o edifício está localizado.  <br/> |
|ZipCode  <br/> |varchar(25)  <br/> |Sim  <br/> |CEP do local do edifício.  <br/> |
|CountryShortCode  <br/> |varchar(2)  <br/> |Sim  <br/> |Códigos ISO 3166-1 alpha-2 do país onde o edifício está localizado.  <br/> |
|StateProvinceCode  <br/> |varchar(3)  <br/> |Sim  <br/> |Abreviação de 3 letras do estado/província onde o edifício está localizado.  <br/> |
|InsideCorp  <br/> |bit  <br/> |Sim  <br/> |Bit que indica se o edifício faz parte da rede corporativa.  <br/> |
|BuildingOfficeType  <br/> |nvarchar(150)  <br/> |Sim  <br/> |Descrição do tipo de escritório do edifício.  <br/> |
|Região  <br/> |varchar(25)  <br/> |Sim  <br/> |Região onde o edifício está localizado.  <br/> |
   
**CqdNetwork**

|**Coluna**|**Tipo de dados**|**Permitir Nulos?**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|Rede  <br/> |varchar(25)  <br/> |Não  <br/> |Endereço da sub-rede.  <br/> |
|NetworkRange  <br/> |tinyint  <br/> |Sim  <br/> |Máscara de sub-rede.  <br/> |
|NetworkNameID  <br/> |int  <br/> |Sim  <br/> |Mapeia opcionalmente para uma linha da tabela CqdNetworkName.  <br/> |
|BuildingKey  <br/> |int  <br/> |Sim  <br/> |Chave estrangeira que deve corresponder à que consta nas entradas da tabela CqdBuilding.  <br/> |
|UpdatedDate  <br/> |datetime  <br/> |Não  <br/> |Data e hora da última atualização da entrada.  <br/> |
   
Por padrão, essa próxima tabela tem uma entrada (0, 'Desconhecido').
  
**CqdBuildingType**

|**Coluna**|**Tipo de dados**|**Permitir Nulos?**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|BuildingTypeId  <br/> |int  <br/> |Não  <br/> |Chave primária da tabela CqdBuildingType.  <br/> |
|BuildingTypeDesc  <br/> |char(18)  <br/> |Não  <br/> |Descrição do tipo de edifício.  <br/> |
   
Por padrão, essa próxima tabela possui uma entrada (0, 'desconhecido', 0, null).
  
**CqdBuildingOwnershipType**

|**Coluna**|**Tipo de dados**|**Permitir Nulos?**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId  <br/> |int  <br/> |Não  <br/> |Chave primária da tabela CqdBuildingOwnershipType.  <br/> |
|OwnershipTypeDesc  <br/> |varchar(25)  <br/> |Não  <br/> |Descrição do tipo de propriedade.  <br/> |
|LeaseInd  <br/> |tinyint  <br/> |Sim  <br/> |Índice que faz referência a outra linha da tabela CqdBuildingOwnershipType, usada para identificar edifícios com concessão.  <br/> |
|Proprietário  <br/> |varchar(50)  <br/> |Sim  <br/> |Proprietário do edifício.  <br/> |
   
Por padrão, essa próxima tabela possui uma entrada (0, 'desconhecido', 0, null).
  
**CqdBssid**

|**Coluna**|**Tipo de dados**|**Permitir Nulos?**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|bss  <br/> |nvarchar(50)  <br/> |Não  <br/> |Chave primária da tabela CqdBssid. É o BSSID do Ponto de Acesso Wi-Fi.  <br/> |
|ess  <br/> |nvarchar(50)  <br/> |Sim  <br/> |Informações do Controlador do Ponto de Acesso Wi-Fi.  <br/> |
|phy  <br/> |nvarchar(50)  <br/> |Sim  <br/> |Informações de phy.  <br/> |
|ap  <br/> |nvarchar(50)  <br/> |Sim  <br/> |Nome do Ponto de Acesso Wi-Fi.  <br/> |
|Edifício  <br/> |nvarchar(500)  <br/> |Sim  <br/> |O Nome do Edifício onde o Ponto de Acesso Wi-Fi está localizado.  <br/> |
   
## <a name="cqd-streams"></a>Fluxos de CQD

Um fluxo de CQD será bom, ruim ou não classificado. O CQM 1.5 agora usa a seguinte definição de CQD:  
  
- Um fluxo ruim é qualquer combinação das métricas de chamada ruins que vão além do limite.
    
- Quando um stream em uma chamada for baixa, ambos os fluxos de chamadas são sinalizadas inválida. Nas conferências, cada participante é contado como uma chamada exclusiva e seja relatado em independentemente de todos os outros.
    
- Fluxos não classificados são aqueles sem métricas de qualidade (ou seja, Transações Sintéticas, chamadas de curta duração).
    
- Fluxos válidos = clientes não móveis
    
- O classificador não pode ser modificado
    
**Classificador/definição de chamada ruim**

|**Métrica**|**Limite**|
|:-----|:-----|
|DDegradationAvg  <br/> |Maior que 1,0 (-1 MOS de rede)  <br/> |
|RoundTrip  <br/> |Maior que 500   <br/> |
|PacketLossRate  <br/> |Maior que 0,1 (10%)   <br/> |
|JitterInterArrival  <br/> |Maior que 30   <br/> |
|RRatioConcealedSamplesAvg  <br/> |Maior que 0,07   <br/> |
   
Definição de JPDR = Definição de chamada ruim menos RatioConcealedSamplesAvg  
  
## <a name="where-is-callercallee"></a>Onde está o Chamador/Autor da Chamada?

CQD não usa os campos de chamador/receptor. Eles têm sido renomeado "Primeiro" e "Segundo" porque há etapas intermediárias entre o chamador e o receptor.
  
 **Primeiro** Será sempre o ponto de extremidade do Servidor (por exemplo, MCU AV; Servidor de Mediação) se houver um Servidor envolvido no fluxo.
  
 **Segundo** Será sempre o ponto de extremidade do Cliente, a menos que seja um fluxo Servidor–Servidor. 
  
**Exemplo de classificação Primeiro e Segundo**

|**UAType do Ponto de Extremidade 1 **|**UUAType do Ponto de Extremidade 2 **|**Primeiro**|**Segundo**|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)   <br/> |4 (Skype for Business)   <br/> |Ponto de Extremidade 1  <br/> |Ponto de Extremidade 2  <br/> |
|2 (AVMCU)   <br/> |1 (mMediationServer)   <br/> |Ponto de Extremidade 2  <br/> |Ponto de Extremidade 1  <br/> |
|4 (Skype for Business)   <br/> |4 (Skype for Business)   <br/> |O Chamador em MediaLine   <br/> |O Autor da Chamada em MMediaLine  <br/> |
   
Se ambos os pontos de extremidade forem do mesmo tipo, o CQD tornará a entrada do Chamador Primeiro e o Autor da Chamada passará a ser o Segundo. Veja mais informações [neste blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).
  
## <a name="accounting-for-vpn"></a>Justificar a VPN

Se a solução de VPN é conhecida precisamente definir o sinalizador VPN, você estará pronto. Caso contrário, use um dos métodos a seguir:
  
- Crie um Tipo de Rede chamado VPN (preferencial), depois Associe Sub-redes de VPN a esse novo NetworkType de VPN.
    
- Crie um edifício chamado VPN, depois Associe Sub-redes de VPN a esse edifício.  
    
## <a name="query-fundamentals"></a>Fundamentos da consulta

Uma consulta bem formada contém todos estes três parâmetros:  
  
- Medição
    
- Dimensão
    
- Filtro
    
Um exemplo de uma consulta bem formada seria "Mostrar-me Fluxos Ruins [Medição] por Sub-rede [Dimensão] para o Edifício 6 [Filtro]".
  
## <a name="what-does-union-do"></a>O que UNION faz?

A união permite filtrar condições usando o operador AND. Há cenários onde você precisa combinar várias condições de filtro para alcançar um resultado como OR
  
Exemplo: quando você precisar obter todos os fluxos de um edifício, UNION proporcionará uma visão distinta do conjunto de dados resultante da fusão. Para usar o parâmetro UNION, insira texto comum no campo UNION nas duas condições de filtro que você deseja unir.  
  
## <a name="default-report-breakdown"></a>Divisão padrão dos relatórios

Se a conexão Sem Fio é gerenciada internamente, você pode recriar os relatórios de conexão Sem Fio no bucket Gerenciado.  
  
![Divisão do relatório de CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a>Processos operacionais

Comece examinando e corrigindo os Fluxos Gerenciados. A qualidade nessa área deve ser de 100% dentro do seu controle e, portanto, mais fácil de corrigir.  
  
### <a name="managed-streams"></a>Fluxos Gerenciados 

Examine e corrija os fluxos gerenciados na seguinte ordem:  
  
1. Servidor-Servidor  
    
2.   Servidor-Com Fio-Dentro
    
3. Com Fio-Com Fio-Dentro  
    
### <a name="unmanaged-streams"></a>Fluxos Não Gerenciados

Examine e corrija os fluxos não gerenciados na seguinte ordem:  
  
1. Servidor-Wi-Fi-Dentro
    
2. Servidor-Com Fio-Fora
    
3. Servidor-Wi_Fi-Fora
    
4. Com Fio-Fora-Direto
    
5. Com Fio-Fora-Retransmissão
    
6. Outros Não Gerenciados
    

