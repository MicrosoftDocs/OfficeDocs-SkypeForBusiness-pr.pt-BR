---
title: Ativar e usar o painel de qualidade da chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre como ativar e usar o painel de qualidade de chamada e obter relatórios resumidos de qualidade das chamadas.
ms.openlocfilehash: 8f1bd778cfa24551d90b0186e606235193a47b0d
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44874264"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Ativar e usar o painel de qualidade de chamada do Microsoft Teams e do Skype for Business Online

Saiba como configurar o Microsoft 365 ou o Office 365 para usar o painel de qualidade da chamada para monitorar a qualidade da chamada.
  
O painel de qualidade de chamada (CQD) fornece informações sobre a qualidade das chamadas feitas usando o Microsoft Teams e os serviços do Skype for Business online. Este tópico descreve as etapas para iniciar a coleta de dados que você pode usar para solucionar problemas de qualidade de chamada.

Atualmente, o CQD e o CQD avançados estão disponíveis para uso. O CQD avançado está disponível em <span>https://cqd.teams.microsoft.com</span> . Nova URL, mas o mesmo logon com as credenciais de administrador.

## <a name="assign-roles-for-accessing-cqd"></a>Atribuir funções para acessar o CQD

Atribua [funções](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD para as pessoas que precisam usá-lo.

Esta tabela mostra o que cada função pode fazer no CQD:


|  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Carregar dados de construção  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global     |Sim          |Sim          |Sim          |Sim         |
|Administrador de Serviço do Teams     |Sim          |Sim          |Sim          |Sim         |
|Administrador de Comunicações de Equipes     |Sim          |Sim          |Sim          |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim          |Sim          |Sim         |Não         |
|Especialista em suporte do teams Communications     |Sim         |Não         |Sim         |Não         |
|Administrador do Skype for Business     |Sim          |Sim          |Sim          |Sim         |
|Leitor global do Azure AD |Sim          |Sim          |Sim         |Não         |
|Leitor de relatórios<sup>1</sup> do Microsoft 365     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> além de ler relatórios do CQD, o leitor de relatórios do Microsoft 365 pode exibir todos os [relatórios de atividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no centro de administração e todos os relatórios do pacote de conteúdo de [adoção do Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se você não estiver vendo EUII (informações identificáveis pelo usuário final) e tiver uma das funções que tem permissão para ver essas informações, lembre-se de que CQD só mantém EUII por 30 dias. Qualquer item mais antigo que 30 dias é excluído.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados do CQD

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Leia [use o Power bi para analisar dados do CQD](CQD-Power-BI-query-templates.md) para saber mais.


## <a name="latest-changes-and-updates"></a>Alterações e atualizações mais recentes


O CQD atualizado (a partir do início de novembro de 2019) oferece um painel de CQDs próximo em tempo real. Os dados do CQD agora estão disponíveis em média em 30 minutos (em comparação com o CQD anterior, que está na média de 24 horas).  O CQD atualizado usa as informações identificáveis do usuário final (EUII), oferecendo aos administradores a capacidade de fazer buscas detalhadas e ampliar no nível do usuário. Também há uma interatividade de relatório para dar suporte a novos cenários, como:


- Qualidade da chamada por região:
  - data por região
  - agregado a uma hora por região
  - locais específicos
  - sub-rede específica
  - usuários ou usuários afetados

- Confiabilidade/falha na chamada por região:
  - data por região
  - agregado a uma hora por região
  - locais específicos
  - sub-rede específica
  - usuários ou usuários afetados

- Classifique minha chamada (RMC) por região: do mês por região agregado a locais específicos para usuários que fornecem classificações de baixa RMC. O CQD v3 também inclui feedback textual.
- Assistência técnica: disponível para um usuário específico em chamadas ponto a ponto ou reuniões, ou para todos os participantes e detalhes da chamada. Ajuda a identificar possíveis problemas do sistema com base no local de rede, dispositivos ou firmware.  
- Versões do cliente: exibir as contagens da sessão e dos usuários para cada versão do cliente ou fazer uma busca detalhada em nomes de usuário para cada versão do cliente. Os filtros predefinidos para o produto e o tipo de cliente ajudam a concentrar as versões em clientes específicos.
- Pontos de extremidade: mostra pontos de extremidade de máquina mapeados para Make/Model of the PC/Mac. Mostra a qualidade agregada por Make/Model. Os dados de mapeamento são carregados de forma semelhante à de construção de dados.

O CQD avançado (v3) também fornece suporte para RBAC, no caso de o acesso EUII não está disponível.  

Um administrador pode gerenciar o Skype for Business Server 2019 (não apenas o Skype for Business Online e o Microsoft Teams) por meio do CQD versão 3. Isso requer uma implementação híbrida e o uso do conector de dados de chamada. Para obter mais informações, consulte [planejar o conector de dados de chamadas](/SkypeForBusiness/hybrid/plan-call-data-connector) .

CQD versão 2 adicionada:

- Dados do Microsoft Teams e do Skype for Business Online
- Os relatórios de resumo incluem um filtro de produto para selecionar todos os dados, dados do Microsoft Teams ou dados do Skype for Business Online
- Vídeo atualizado e lógica de classificação de qualidade do fluxo VBSS. Consulte [classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md) para as definições do classificador.

Consulte este artigo para obter uma lista de [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Para ver informações sobre atualizações e alterações no painel, clique no link nas **boas notícias!** faixa quando ele é exibido no painel.

O CQD versão 1 fornecido com o Skype for Business Server 2015 tem os seguintes recursos:

- Acesso a dados de relatório armazenados em cache para acesso rápido
- Links profundo para páginas de relatório para compartilhamento e publicação de informações
- Edição e criação de relatórios otimizadas e metadados editáveis para descrições de relatórios
- APIs da Web que dão acesso programático aos dados do cubo para uso em painéis personalizados

## <a name="cqd-near-real-time-nrt-data"></a>Dados CQD (NRT) ao redor do tempo real

O CQD avançado (v3, lançado em novembro de 2019) usa um feed de dados quase em tempo real. Os registros de chamadas estão disponíveis no portal do CQD em média em 30 minutos (em comparação com o CQD anterior, que está na média de 24 horas). Os registros de chamadas do pipeline do NRT só estão disponíveis por alguns meses antes de serem removidos do conjunto de dados. O CQD v3 combina dados do pipeline v2 atual com dados do NRT do pipeline v3. As consultas nos portais V2 e v3 dos dados do período de arquivamento produzem os mesmos resultados. As consultas de dados V2 e V3 para os dados do NRT e os dados do NRT + períodos PII serão diferentes.

### <a name="piieuii-data"></a>Dados PII/EUII

Os dados PII ou EUII são apenas do pipeline v3. Devido a motivos de conformidade, os dados PII/EUII são mantidos por 30 dias. Como os dados do NRT atravessam a marca de 30 dias, os campos PII/EUII são apagados, resultando em dados de NRT de PII grátis. Os campos PII/EUII são:

- Endereço IP completo
- Endereço de controle de acesso à mídia (MAC)
- Identificador do conjunto de serviços básico (BSSID)
- URI de protocolo SIP (protocolo de iniciação de sessão) (somente Skype for Business)
- Nome UPN
- Nome do ponto de extremidade do computador
- Feedback textual do usuário
- ID do objeto (a ID de objeto do Active Directory do usuário do ponto de extremidade)

### <a name="date-controls"></a>Controles de data

O CQD v3 adiciona os seguintes novos tipos de tendência contínua:

- 5 dias
- 7 dias
- 30 dias
- 60-dia
- 90-dia

O parâmetro de data de URL agora pode aceitar um campo Day. Os relatórios de dia transcorrido usam datas especificadas no formato AAAA-MM-DD como o último dia da tendência.  O parâmetro de data de URL "00" indica "hoje".

|URL| Data de término da tendência do dia transcorrido|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02/</span>   |Dia atual de fevereiro de 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02-15/</span>|15 de fevereiro de 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /00/</span>        |Dia atual|
|||

Por padrão, o dia atual do mês é usado como o último dia da tendência do dia transcorrido.

### <a name="drill-thru-functionality"></a>Funcionalidade de Drill-through

O CQD v3 oferece suporte ao uso de campos Drill through ou Drill down nos relatórios SPD. Se esses campos de dimensão estiverem selecionados, o relatório abrirá automaticamente uma guia de relatório diferente e filtrará o valor selecionado. Os campos com um filtro de Drill-through atribuído são diferenciados por um ícone de cursor diferente (o ponteiro) quando você passa o mouse sobre eles.

Quando um campo Drill-through é selecionado, o painel navega automaticamente para a guia nova e especificada e aplica um filtro com o valor selecionado. Se essa guia tiver seus próprios campos Drill through e um estiver selecionado, os filtros detalhados anteriores e os novos encaminharão para a nova propagação. Isso permite que você crie um relatório que restrinja progressivamente o conjunto de dados resultante.

Por exemplo, em um relatório de Drill-through de qualidade de chamada, um usuário pode clicar na data em que gostaria de "analisar", o que leva à guia local.

![Captura de tela: mostra o relatório Drill-through](media/CQD-drill-thru-report.png)

Você pode adicionar várias datas na guia local, como adicionar 2019-09-22 a data: 2019-09-24: 

![Captura de tela: adicionar uma data ao relatório de Drill-through](media/CQD-add-date.png)

> [!NOTE]
> Não vá diretamente para a última guia. Sem filtros selecionados em um Drill-through anterior, o resultado será muito grande para ser mostrado em uma tabela.

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Ativar relatórios de resumo do Microsoft Call Quality Dashboard (CQD)

Antes de começar a usar o CQD, ative-o para o Microsoft 365 ou o Office 365 da seguinte maneira:

![Um ícone que mostra o logotipo do Microsoft Teams ](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**

1. Entre em seu Microsoft 365 ou no Office 365 usando a conta de administrador do Microsoft Teams Service e, em seguida, selecione o bloco **administrador** para abrir o centro de administração.
2. No painel esquerdo, em **centros de administração**, selecione **Microsoft Teams** para abrir o centro de administração do Microsoft Teams.
3. No centro de administração do Microsoft Teams, selecione **painel de qualidade de chamada** no painel esquerdo.
4. Na página que abre \( https:// <span> CQD.Teams.Microsoft.com <span/> \) , clique em **entrar** e digite sua conta de administrador global ou as informações da conta de administrador do Microsoft Teams Service.

    ![Captura de tela: mostra o prompt de credenciais](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Depois de entrar, uma vez ativada, o CQD começará a coletar e processar dados.  
> [!NOTE]
> Pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

![Um ícone do logotipo do Skype for Business ](media/sfb-logo-30x30.png) **usando o portal herdado do Skype for Business**

1. Entre em seu Microsoft 365 ou no Office 365 usando uma conta de administrador e, em seguida, selecione o bloco **administrador** para abrir o centro de administração.
2. No painel esquerdo, em **centros de administração**, selecione **Microsoft Teams** para abrir o centro de administração do Microsoft Teams.
3. No centro de administração do Microsoft Teams, selecione **portal herdado** no painel esquerdo, selecione **ferramentas**e, em seguida, selecione **painel de qualidade de chamada do Skype for Business online**.

     ![Captura de tela: selecione o painel de qualidade da chamada](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Na página que é aberta, entre com sua conta de administrador global e forneça as credenciais da conta quando for solicitado.

Depois de entrar, quando ativado, o painel de qualidade da chamada começará a coletar e processar dados.

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Recursos do painel de qualidade de chamada do Microsoft Teams e do Skype for Business Online

<a name="BKMKFeaturesOfTheCQD"> </a>


CQD relatórios de resumo fornecem um subconjunto de recursos planejados para relatórios detalhados. As diferenças entre as edições são resumidas aqui:
  
|Recurso|Relatórios de resumo|Relatórios detalhados|
|:--- |:--- |:--- |
|Métrica de compartilhamento de aplicativos | Não | Sim |
|Suporte a informações de prédio do cliente | Sim | Sim |
|Suporte a informações de ponto de extremidade do cliente | Somente no <span> CQD.Teams.Microsoft.com<span/> | Somente no <span> CQD.Teams.Microsoft.com<span/> |
|Suporte para análise de busca detalhada   | Não   | Sim   |
|Métricas de confiabilidade de mídia   | Não   | Sim   |
|Relatórios prontos da caixa   | Sim   | Sim   |
|Relatórios de visão geral   | Sim   | Sim   |
|Conjunto de relatórios por usuário   | Não   | Sim   |
|Personalização do conjunto de relatórios (adicionar, excluir, modificar relatórios)   | Não   | Sim   |
|Métricas de compartilhamento de tela com base em vídeo   | Não   | Sim   |
|Métricas de vídeo   | Não   | Sim   |
|Quantidade de dados disponíveis   | Últimos 12 meses   | Últimos 12 meses   |
|Dados do Microsoft Teams   | Sim   | Sim   |
| | | |

### <a name="out-of-the-box-reports"></a>Relatórios prontos da caixa

Todas as edições do CQD fornecem uma experiência que oferece métricas de qualidade de chamada sem a necessidade de criar novos relatórios. Depois que os dados forem processados no back-end, você verá dados de qualidade da chamada nos relatórios.

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.
  
### <a name="overview-reports"></a>Relatórios de visão geral

Todas as edições da CQD fornecem um ponto de entrada de alto nível para as informações gerais de qualidade da chamada, mas a maneira pela qual as informações são apresentadas em relatórios de resumo é diferente dos relatórios detalhados.  
  
Os relatórios de resumo fornecem uma exibição de relatório de página com guias simplificada para que você possa navegar rapidamente e entender o status e as tendências gerais de qualidade das chamadas.

As quatro guias incluem:
  
- **Qualidade de chamadas gerais** — fornece informações sobre todos os fluxos, que é uma agregação que mostra tendências mensais e diárias para:
  - Server-streams do cliente
  - Cliente-fluxos de cliente
  - Fluxos cliente/cliente e cliente separado
- **Servidor — cliente** — fornece detalhes dos fluxos entre pontos de extremidade do servidor e do cliente.
- **Cliente** — fornece detalhes para os fluxos entre dois pontos de extremidade do cliente.
- **SLA de qualidade de voz** — fornece informações sobre chamadas incluídas no SLA de qualidade de voz do Skype for Business online.

> [!NOTE]
> O CQD versão 3 funciona com o Microsoft Teams, o Skype for Business Online e o Skype for Business Server. Para usar o CQD com o Skype for Business Server 2019, você terá que [Configurar o conector de dados de chamadas](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [planejar ligar para conector de dados](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.

- Qualidade da chamada por região:

  - data por região
  - agregado a uma hora por região
  - locais específicos
  - sub-rede específica
  - usuários ou usuários afetados

- Confiabilidade/falha na chamada por região:
  - data por região
  - agregado a uma hora por região
  - locais específicos
  - sub-rede específica
  - usuários ou usuários afetados

- Classifique minha chamada (RMC) por região: do mês por região agregado a locais específicos para usuários que fornecem classificações de baixa RMC. O CQD v3 também inclui feedback textual.
- Assistência técnica: disponível para um usuário específico em chamadas ponto a ponto ou reuniões, ou para todos os participantes e detalhes da chamada. Ajuda a identificar possíveis problemas do sistema com base no local de rede, dispositivos ou firmware.  
- Versões do cliente: exibir as contagens da sessão e dos usuários para cada versão do cliente ou fazer uma busca detalhada em nomes de usuário para cada versão do cliente. Os filtros predefinidos para o produto e o tipo de cliente ajudam a concentrar as versões em clientes específicos.
- Pontos de extremidade: mostra pontos de extremidade de máquina mapeados para Make/Model of the PC/Mac. Mostra a qualidade agregada por Make/Model. Os dados de mapeamento são carregados de forma semelhante à de construção de dados.

### <a name="overall-call-quality-tab"></a>Guia qualidade geral da chamada

Use os dados nesta guia para avaliar o status e as tendências da qualidade da chamada com base em contagens de fluxo e percentuais insatisfatórios. A legenda no canto superior direito mostra quais elementos visuais e de cor representam essas métricas.
  
![Captura de tela: mostrar a guia qualidade da chamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Os fluxos são classificados em três grupos: satisfatório, fraco e não classificados. Também são calculados valores de *baixa qualidade* que proporcionam a taxa de fluxos classificados como *deficientes* para a contagem total de fluxos classificados. Como *baixa% = fluxos ruins/(fluxos de má qualidade + bom fluxo) * 100*, os *% deficientes* não são afetados pela presença de vários fluxos não *classificados* . Para ver o que classifica um fluxo como ruim ou bom, consulte [classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md).
  
Use a escala à esquerda para medir os valores de contagem de fluxo.
  
![Captura de tela: mostra os valores de contagem de fluxo](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use a escala à direita para medir os valores de baixa%.
  
![Captura de tela: mostra valores de baixa qualidade](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Você também pode obter os valores numéricos reais passando o mouse sobre uma barra.
  
> [!NOTE]
> O exemplo a seguir é de um conjunto de dados de exemplo muito pequeno, e os valores não são realistas para uma implantação real.
  
![Captura de tela: mostra o mouse usado para acessar dados](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
O volume de fluxo geral ajuda a determinar a relevância das porcentagens insatisfatórias calculadas. Quanto menor for o volume de fluxos gerais, menos confiável será a porcentagem dos valores de porcentagem deficientes reportados.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Guias servidor-cliente e cliente-cliente

Essas duas guias fornecem detalhes para os fluxos que ocorreram em seus cenários de ponto de extremidade a ponto de extremidade. A guia servidor-cliente tem quatro seções recolhíveis que representam quatro cenários em que os fluxos de mídia fluiriam.
  
- Com fio interno
- Com fio externo
- Sem fio dentro
- Sem fio externo

Da mesma forma, a guia cliente/cliente tem cinco seções recolhíveis:

- Com fio interno – com fio dentro
- Com fio interno – com fio externo
- Com fio externo — com fio externo
- Com fio interno — WiFi Inside
- Com fio interno — WiFi externo

#### <a name="inside-test"></a>Teste interno

Durante o processamento, o back-end do CQD classifica um fluxo como *interno* ou *externo* usando as informações de construção, se houver. Os pontos de extremidade de cada fluxo estão associados a um endereço de sub-rede. Se a sub-rede estiver na lista das sub-redes marcadas InsideCorp nas informações de construção carregadas, ela será considerada *dentro*. Se as informações de construção ainda não tiverem sido carregadas, então dentro do teste sempre classifica os fluxos como *fora*.  

> [!NOTE]
> O teste interno para um cenário de servidor-cliente apenas considera o ponto de extremidade do cliente. Como os servidores estão sempre fora da perspectiva de um usuário, isso não é contabilizado no teste.
  
#### <a name="wired-vs-wifi"></a>Com fio versus WiFi

Conforme os nomes indicam, os critérios de classificação são baseados no tipo de conexões de cliente. Novamente, o servidor é sempre conectado e não está incluído no cálculo.
  
> [!NOTE]
> Dado um fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, ele será classificado como WiFi no CQD.
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selecionando dados do produto para ver nos relatórios

<a name="BKMKProductFilter"></a>

Nos relatórios avançados de resumo e de localização, você pode usar o menu suspenso **filtro do produto** para mostrar todos os dados do produto, somente dados do Microsoft Teams ou somente dados do Skype for Business online.
  
![Captura de tela: mostra as opções de controle de filtro do produto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Em relatórios detalhados, você pode usar a dimensão **is Teams** para filtrar os dados para o Microsoft Teams ou dados do Skype for Business online.
  
## <a name="upload-tenant-data-information"></a>Carregar informações de dados do locatário

<a name="BKMKTenantDataInformationUpload"></a>

O painel relatórios de resumo CQD inclui uma página de **carregamento de dados de locatários** , acessada selecionando **carregar dados do locatário** no menu configurações no canto superior direito. Esta página é usada para os administradores carregarem suas próprias informações, como:

- Um mapa de endereço IP e informações geográficas
- Um mapa de cada AP sem fio e seu endereço MAC
- Um mapa de ponto de extremidade para marca/modelo/tipo de ponto de extremidade, etc.
  
> [!NOTE]
> Os rótulos de relatório que você carrega no CQD serão tratados como *dados de suporte* em seu contrato com o Microsoft 365 ou o Office 365, incluindo qualquer informação que, de outra forma, seria considerada dados do *cliente* ou *dados pessoais*. Não inclua os dados que não deseja fornecer à Microsoft como *dados de suporte*, essas informações ficarão visíveis aos engenheiros da Microsoft para fins de suporte.

![Captura de tela: mostra os dados do locatário do painel de qualidade da chamada](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Na página de **carregamento de dados do locatário** , use o menu suspenso para escolher um tipo de arquivo de dados para carregar. O tipo de dados arquivo denota o conteúdo do arquivo (por exemplo, "edifício" refere-se ao mapeamento do endereço IP e à criação e outras informações geográficas, "ponto de extremidade" refere-se ao mapeamento do nome do ponto de extremidade nas informações de tipo/modelo/tipo de ponto de extremidade). Atualmente, o CQD é compatível com os tipos de dados "edifício" e "ponto de extremidade" do cqd.teams.microsoft.com (no estágio de visualização e ainda não está disponível oficialmente), cqd.lync.com só oferece suporte ao tipo de dados "edifício".



2. Depois de selecionar o tipo de dados do arquivo, clique em **procurar** para escolher um arquivo de dados.

   - Um arquivo de dados deve ser um arquivo. TSV (valores separados por tabulação) ou um arquivo. csv (valor separado por vírgula). Com um arquivo. csv, qualquer campo que contenha vírgula deve estar entre aspas ou ter a vírgula removida. Por exemplo, se o seu nome de edifício for RJ, RJ, digite "NY, NY" no arquivo. csv.
   - O arquivo de dados não deve ser maior do que 50 MB.
   - Os arquivos carregados no cqd.teams.microsoft.com têm um limite de linha expandido de 1 milhão para manter o desempenho da consulta rápido. Esse limite também se aplica a CQD V2 em CQD <span></span> . Lync <span></span> . com.
   - Para cada arquivo de dados, cada coluna no arquivo deve corresponder a um tipo de dados predefinido, discutido posteriormente neste tópico.
3. Em seguida, especifique uma **data de início** e, opcionalmente, **especifique uma data de término**.
4. Por fim, selecione **carregar** para carregar o arquivo no servidor do CQD.
    Antes de o arquivo ser carregado, ele é validado primeiro. Uma vez validada, ela é armazenada em um blob do Azure. Se ocorrer uma falha na validação ou o arquivo não for armazenado em um blob do Azure, uma mensagem de erro solicitará uma correção para o arquivo. A imagem a seguir mostra um erro de exemplo com um número incorreto de colunas no arquivo de dados.

     ![Captura de tela: mostra um erro de validação de carregamento](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se não ocorrerem erros durante a validação, o upload do arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregado na tabela **My uploads** . A parte inferior dessa página também mostra uma lista completa de todos os arquivos carregados para o locatário atual.
    Cada registro mostra um arquivo de dados do locatário carregado, com o tipo de arquivo, a hora da última atualização, o período de tempo, a descrição, um ícone de remoção e um ícone de download. Para remover um arquivo, selecione o ícone de lixeira na tabela. Para baixar um arquivo, selecione o ícone baixar na coluna **baixar** da tabela.

     ![Captura de tela: mostra a tabela My uploads](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Se você optar por usar vários arquivos de dados de construção ou vários arquivos de dados de ponto de extremidade, alguns relatórios gerarão mais lentamente.

### <a name="tenant-data-file-format-and-structure"></a>Estrutura e formato de arquivo de dados do locatário

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Criando arquivo de dados

O CQD usa um arquivo de construção de dados, que ajuda a fornecer detalhes úteis de chamadas. A coluna de sub-rede é derivada expandindo a coluna Network + NetworkRange e, em seguida, ingressando na coluna subnet na primeira sub-rede ou segunda coluna do registro de chamada para mostrar as informações de construção, cidade, país ou região. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes do carregamento:

Você pode baixar um modelo de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)
  
- O arquivo deve ser um arquivo. TSV (as colunas são separadas por uma TABULAção) ou um arquivo. csv (as colunas são separadas por uma vírgula).
- O arquivo de dados não inclui uma linha de cabeçalho de tabela. Espera-se que a primeira linha do arquivo de dados seja dados reais, e não rótulos de cabeçalho como "rede".
- Os tipos de dados no arquivo só podem ser String, Integer ou Boolean. Para o tipo de dados inteiro, o valor deve ser um valor numérico. Os valores Boolianos devem ser 0 ou 1.
- Se uma coluna usa o tipo de dados de cadeia de caracteres, um campo de dados pode estar vazio, mas ainda deve ser separado por uma Tabulação ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazia.
- Deve haver 14 colunas para cada linha (ou 15 se você quiser adicionar a coluna opcional), cada coluna deve ter o tipo de dados apropriado, e as colunas devem estar na ordem listada na seguinte tabela:

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**Nome do campo da coluna**|NetworkIP  |NetworkName              |NetworkRange|BuildingName  |Propriedadetype| Buildingtype  |BuildingOfficeType|Cidade   |ZipCode|País|Estado |Região|InsideCorp&dagger;|ExpressRoute&Dagger;|VPN (opcional)|
|**Tipo de dados**        | Cadeia de caracteres    | Cadeia de caracteres                  |Número      | Cadeia de caracteres       | Cadeia de caracteres      | Cadeia de caracteres        |Cadeia de caracteres            |Cadeia de caracteres |Cadeia de caracteres |Cadeia de caracteres |Cadeia de caracteres|Cadeia de caracteres|Boolean   |Boolean     |Boolean|
|**Valor de exemplo**    |192.168.1.0|EUA/Seattle/SEATTLE-SEA-1| 26         | SEATTLE-SEA-1| Contoso.com     | Terminações|Engineer       |Seattle|98001  |Junte     |WA    |MSUS  | 1        |0           | 0|
|||||||||||||||||

&dagger;Essa configuração pode ser usada para refletir se a sub-rede está ou não dentro da rede corporativa. Você pode personalizar o uso para outras finalidades se decidir.

&Dagger;Essa configuração pode ser usada para refletir se a rede usa o Azure ExpressRoute. Você pode personalizar o uso para outras finalidades se decidir.  

**Linha de amostra:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema antes de carregá-lo novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para prédios nos relatórios. Algumas implementações de VPN não reportam precisamente as informações de sub-rede. É recomendável que, ao adicionar uma sub-rede VPN ao arquivo de construção, em vez de uma entrada para a sub-rede, as entradas separadas sejam adicionadas para cada endereço na sub-rede VPN como uma rede de 32 bits separada. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive.
>
> A coluna VPN é opcional e será definida como padrão 0.  Se o valor da coluna VPN estiver definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede.  Use isso de maneira moderada e somente para sub-redes VPN, já que expandir totalmente essas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a construção de dados.

### <a name="endpoint-data-file"></a>Arquivo de dados de ponto de extremidade

O CQD usa um arquivo de dados de ponto de extremidade. Os valores de coluna são usados na coluna nome do ponto de extremidade do primeiro cliente ou segundo nome do ponto de extremidade do cliente para mostrar informações sobre tipo, modelo ou marca de ponto de extremidade. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes do carregamento:

- O arquivo deve ser um arquivo. TSV (as colunas são separadas por uma TABULAção) ou um arquivo. csv (as colunas são separadas por uma vírgula).
- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Espera-se que a primeira linha do arquivo de dados seja real, não um rótulo de cabeçalho como "EndpointName".
- Todas as sete colunas usam somente o tipo de dados de cadeia de caracteres. O comprimento máximo permitido é de 64 caracteres.
- Um campo de dados pode estar vazio, mas ainda deve ser separado por uma Tabulação ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazia.
- EndpointName deve ser exclusivo; caso contrário, o carregamento falhará. Se houver uma linha duplicada ou duas linhas com o mesmo ponto de extremidadename, o conflito causará a junção incorreta.
- EndpointLabel1, EndpointLabel2 e EndpointLabel3 são rótulos personalizáveis. Elas podem ser cadeias de caracteres ou valores vazios, como o "departamento de ti designado 2018 laptop" ou "marca do ativo 5678".
- Deve haver sete colunas para cada linha, e as colunas devem estar na seguinte ordem:

  **Ordem dos campos:**

EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Linha de amostra:**

"1409W3534, fabricante do 123, modelo da Fabrikam 123, laptop, designado para laptop 2018, etiqueta de ativo 5678, comprar 2018

## <a name="migrate-reports-from-previous-version-of-cqd"></a>Migrar relatórios de uma versão anterior do CQD

Se você criou relatórios ou carregou arquivos de dados locatários (mapeamento) para o CQD para o Skype for Business ( https://cqd.lync.com) e deseja migrá-los para o CQD for Teams ( https://cqd.teams.microsoft.com) , veja como:

1.    Vá para [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) e navegue até o conjunto de relatórios que você deseja exportar. 
2.    Passe o mouse sobre o relatório e, na guia "..." , escolha **Exportar árvore de relatório**. Salve o arquivo de exportação.
3.    Acesse [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/) e navegue até o local onde deseja importar os relatórios.
4.    Nos links à esquerda, clique em **importar** e selecione o arquivo exportado. 
5.    Após a importação dos relatórios, você verá esta mensagem: "a importação do relatório foi bem-sucedida. O novo relatório foi adicionado ao final do conjunto de relatórios. " 


## <a name="create-custom-detailed-reports"></a>Criar relatórios detalhados personalizados

Se você acha que deseja criar um relatório específico que se concentre em uma dimensão dos dados de uma maneira que os relatórios detalhados fornecidos não o fazem, crie um relatório personalizado.

Na lista suspensa de relatórios na parte superior da tela exibida ao fazer logon \( na tela **relatórios resumidos** , \) selecione **relatórios detalhados** e, em seguida, **novo** d clique em "Editar" no menu Ação de um relatório para ver o editor de consultas. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O editor de consultas ajuda você a editar essas consultas e as opções de exibição do relatório. Ao abrir o editor de consultas para um novo relatório, você verá algo semelhante a esta captura de tela:

![Editar novos relatórios](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensões, medidas e filtros são escolhidos no painel esquerdo. Clique no botão "mais" ao lado de um título para abrir a caixa de diálogo onde você pode adicionar uma dimensão, medida ou filtro e marque a caixa correspondente. Se você editar um relatório existente, poderá desmarcar os valores existentes para removê-los. Para obter detalhes, consulte [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).
2. As opções para a personalização de gráficos são exibidas na parte superior.
3. Uma visualização do relatório está disponível no editor de consultas.
4. Um nome de relatório detalhado e uma descrição podem ser criados com a caixa de edição na parte inferior.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Por que o CQD marca uma chamada como "boa" se um ou mais participantes da reunião tivessem uma experiência ruim?

Confira as regras que o CQD usa para [classificação de fluxo](stream-classification-in-call-quality-dashboard.md).
 
Para fluxos de áudio, qualquer um dos cinco classificadores, que são calculados para a média com base na duração da chamada, pode estar dentro dos parâmetros "bom". Não significa que os usuários não perceberam algo que contribuiu para um cancelamento de áudio, estático ou falha. 

Para determinar se foi um problema de rede, examine o Delta entre os valores médios da sessão e os valores máximos. O máximo de valores é o número máximo detectado e informado durante a sessão.
 
Veja um exemplo de como solucionar essa situação. Digamos que você tenha um rastreamento de rede durante uma chamada e os primeiros 20 minutos não há nenhum pacote perdido, mas você tem um intervalo de 1,5 segundos de pacotes e, em seguida, bom para o restante da chamada. A média será <10% (0,1) perda de pacotes mesmo em uma análise do Wireshark Trace RTP. Qual foi o máximo de perda de pacote? 1,5 segundos em um período de 5 segundos seria de 30% (0,3). Isso ocorreu dentro do período de amostragem de cinco segundos (talvez ou pode ser dividido no período de amostragem)?
 
Se as métricas de rede estiverem boas nos valores médias e máximos, procure outros dados de telemetria: 
- Verifique a taxa de eventos insuficientes da CPU para ver se os recursos de CPU detectados disponíveis eram insuficientes e causaram má qualidade. 
- O dispositivo de áudio está em modo Half duplex para evitar comentários devido aos microfones que estão prestes a ser fechados para os alto-falantes? 
- Verifique a taxa de evento de AEC duplex do dispositivo. O dispositivo está ocorrendo ou o microfone está apresentando ruído ou estático devido a esgotamentos de áudio USB quando conectado a um Hub ou uma docking Station:  
- Verifique as taxas de evento de falhas do dispositivo e do microfone. O próprio dispositivo está funcionando corretamente?  
- Verifique as taxas de eventos de captura e renderização que não estão funcionando.


Para saber mais sobre dimensões e medidas disponíveis na telemetria do CQD, consulte [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).

Para ruído de fundo, marque a taxa de evento de mudo para ver a quantidade de tempo em que os participantes estavam em mudo.
 
Crie relatórios detalhados no CQD e filtre a ID da reunião para ver todos os usuários e fluxos em uma reunião e adicionar os campos dos quais você está interessado. Um usuário que informa que o problema pode não ser o que estava com o problema. Ele está apenas relatando a experiência.
 
A telemetria não irá necessariamente chamar o problema, mas pode ajudá-lo a entender melhor onde procurar e informar suas decisões. É uma rede, dispositivo, atualizações de driver ou firmware, uso ou usuário?

### <a name="why-do-i-see-upto-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Por que vejo até 0,2% diferença de valores de contagem de usuários e chamada em medidas e como obter os volumes mais precisos? 
Para calcular a contagem de chamadas e os indicadores de contagem do usuário, uma operação cont.se diferente é realizada em relação à chamada ou aos identificadores de usuário no conjunto de dados. Em conjuntos de dados grandes, há um erro de até 0,2% inerente à operação cont.se distinta. Para o volume mais preciso, você deve confiar em medidas de contagem de fluxo, pois elas não dependem dessa operação cont.se distinta. A filtragem para reduzir o volume dos dados pode reduzir o erro, mas não pode eliminar essa fonte de erro em chamadas distintas e contagens de usuários. Consulte [dimensões e medidas disponíveis no painel de qualidade de chamada](dimensions-and-measures-available-in-call-quality-dashboard.md) para quais medidas são impactadas.

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Por que meus dados de relatório do CQD v2 parecem diferentes dos dados do relatório do CQD v3? 

Se você vir diferenças de dados entre CQD V2 e v3, certifique-se de que a comparação de dados ou a validação seja feita em um ' maçãs-a-maçãs ' e nível estreito, e não em um nível agregado. Por exemplo, se você filtrar os dois relatórios para os dados de cliente da área de trabalho de MSIT "Building 30" do teams WiFi, o percentual de baixa qualidade deve ser o mesmo entre V2 e v3.

A classificação CQDv2 para CallSetup falha só é considerada para a modalidade de "áudio", em CQDv3 essa classificação ocorre para cada modalidade (áudio, vídeo e compartilhamento) e é representada no respectivo fluxo de modalidade. 

Para o Teams, o CQDv2 aplica os mesmos comentários dos usuários a todas as modalidades CQDv3 aplica a base de feedback sobre a modalidade para equipes.

O CQD v3 inclui 
1. Chamadas do Skype for Business Server 2019, 
2. Chamadas do Skype bot, como: atendedor automático, fila de chamadas, serviço de anúncio de conferência, 
3. Interface da área de trabalho virtual,
4. Interoperabilidade de vídeo em conferência
3. Chamadas do Publisher e do apresentador de eventos ao vivo 
4. Chamadas PSTN. 

Por exemplo, se você vir fluxos de áudio do 200.000 com falhas de 5000 em um relatório de resumo do CQD v2, não seria comum ver os fluxos de áudio do 300.000 com falhas de 5500 (a diferença pode ser devido ao Skype for Business 2019 Server que permite chamadas, chamadas CVI, chamadas PSTN e assim por diante) em um relatório de resumo CQD v3.

Para desambiguar diferenças inesperadas, examine mais de uma divisão dos dados gerais. Filtrar os dados por um ou mais dos seguintes parâmetros:

- Par de categorias de agente do usuário
- Primeiro produto
- Segundo produto

Veja um exemplo da aplicação de filtros específicos para comparar os dados do CQD V2 e do CQD V3:

1. Registro de QoE disponível = verdadeiro

2. Adicionar é o filtro de pares do servidor com o valor: cliente: cliente e cliente: servidor. A maioria dos locatários prefere excluir o servidor: chamadas do servidor.

3. Adicionar um filtro para categoria do agente do usuário e filtrar atendedor automático, fila de chamadas, bot, sistema de sala, MediationServer, serviço de anúncio de conferência, VDI, etc.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="Captura de tela da aplicação de filtros específicos no CQD v3":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="Captura de tela da aplicação de filtros específicos no CQD v2":::

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Outras diferenças esperadas entre CQD V2 e CQD v3

Há vários aprimoramentos de qualidade e confiabilidade no Teams, mas não no Skype for Business Online:

- Reconexão automática
- Roaming rápido
- Gerenciamento de BW aprimorado

Ao comparar dados para estes dois serviços:

- Escolha um cenário com foco justo, como conexões corporativas com fio, áreas de trabalho do Windows ou uma única região ou prédio.
- Verifique as faixas de IP do teams Sr, TR ou MP. Os intervalos do teams são mais recentes do que o Skype for Business Online, e isso pode causar problemas de conectividade que envolvem firewalls
- Não compare os números de resumo ou de nível superior. Essas comparações levarão você a comparar uma grande quantidade de chamadas do Skype for Business online em uma conexão com fio de empresa a um pequeno volume de chamadas do teams em uma rede LTE ou privada.
- Cuidado com as diferenças de diferença de localização e população: há muitas comparações muito diferentes para serem úteis:
  - NOAM: ÁSIA-PACÍFICO
  - NY: Goa
  - Com fio: WiFi
  - Rede corporativa: rede doméstica
  
### <a name="why-cant-i-see-euii-in-cqd"></a>Por que não consigo ver o EUII no CQD?

Essas funções de administrador podem acessar o CQD, mas não podem ver EUII (informações identificáveis pelo usuário final):
- Leitor de relatórios do Microsoft 365
- Especialista em suporte do teams Communications

Para saber mais sobre as funções que podem acessar o CQD-, incluindo EUII, [atribua funções para acessar o CQD](#assign-roles-for-accessing-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Por que estou vendo as informações do Skype for Business no CQD quando já filtro para o Microsoft Teams?

Ao filtrar para equipes somente nos relatórios do CQD (isteams = 1), você está filtrando todas as chamadas em que o *primeiro ponto de extremidade* é Teams. Se o *segundo ponto de extremidade* for o Skype for Business, essas informações serão exibidas no seu relatório do CQD.

## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 
