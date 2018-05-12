---
title: Qualidade da experiência Revise o guia para equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guia para analisar o desempenho de mídia em tempo real for Microsoft Teams usando o painel de controle de qualidade de chamada (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e6ee8ac7201aad39e6dd3af8887854f080f8a60
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="quality-of-experience-review-guide"></a>Qualidade da experiência Revise o guia

Este guia é sobre a fase de unidade de valor para o Microsoft Teams e Skype para negócios Online. Você pode [baixar uma versão do Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) deste guia.

## <a name="introduction"></a>Introdução

Para que o maior impacto sobre como melhorar a experiência do usuário, as organizações precisam tornem operacional as principais áreas que são mostradas na figura a seguir.
Áreas adicionais incluem identificando tarefas operacionais, estabelecimento de metas para métricas de qualidade, averiguar as métricas usar para medir o êxito organizacional e estreitando áreas de investigação conforme necessário.

![Principais áreas para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuário, dispositivos e clientes.](media/quality-of-experience-review-guide-image1.png)

_Figura 1 - operacionais áreas de chave abordadas neste documento_

Continuamente avaliando e correção as áreas descritas neste documento, você pode reduzir seu potencial para afetar negativamente a qualidade da experiência dos usuários. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta

-   Baixa cobertura de Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Versões do cliente inconsistentes ou desatualizadas

-   Dispositivos de áudio não otimizados ou internos

-   Sub-redes problemáticos ou dispositivos de rede

Através de planejamento adequado e design antes de implantar equipes ou Skype para Business Online, você pode reduzir a quantidade de esforço que serão necessários para manter experiências de alta qualidade.

Este guia se concentra no uso do Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área, com uma ênfase especial para maximizar a adoção e o impacto de áudio. Todos os aprimoramentos feitos à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

Para acelerar sua avaliação, dois modelos CQD curated são fornecidos: um para o gerenciamento de todas as redes e o outro fosse filtrada para gerenciados apenas as redes (internas). Embora os relatórios de modelo de todas as redes são configurados para exibir informações de rede e de construção, ele ainda pode ser usado enquanto você trabalha em direção a coleta e carregamento de informações de construção. Carregar informações em CQD do edifício habilita o serviço aperfeiçoar os relatórios adicionando informações personalizadas de construção, rede e local enquanto distinguir interna do sub-redes externos. Para obter mais informações, consulte [mapeamento de construção](#building-mapping) posteriormente neste documento.

### <a name="what-is-the-cqd"></a>Qual é o CQD?

Use o painel de qualidade de chamada (CQD) para obtém ideias sobre a qualidade das chamadas feitas por meio de equipes e Skype para serviços corporativos. CQD foi projetado para ajudar Skype para os administradores corporativos e as equipes e os engenheiros de rede otimização a rede. CQD analisa agregam informações para uma organização inteira onde padrões gerais podem se tornar aparentes, permitindo que a equipe efetue informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de chamada que lhe dão ideia da experiência do usuário, confiabilidade de chamada e qualidade geral da chamada.

> [!NOTE]
> CQD não contém informações de identificação pessoal (PII). PII é informações que podem ser usadas por conta própria ou com outras informações para identificar, entre em contato ou localizar uma única pessoa ou para identificar um indivíduo em contexto. 

### <a name="intended-audience"></a>Público-alvo

Este documento é destinado a ser usado pelo parceiro e cliente participantes com funções como arquiteto/líder de colaboração, consultor, especialista da adoção do gerenciamento de alteração, ajuda/suporte de liderança de mesa, liderança de rede, liderança de área de trabalho e administrador de TI.

Este documento também se destina a ser usado pelo champion(s) a qualidade designada.
Para obter mais informações, consulte [a função campeão de qualidade](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este guia, verifique se que você tem as [funções](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) de locatário adequadas atribuído para que você possa acessar CQD.

-   **Função Administrador Global do office 365:** Acessa todos os recursos administrativos no conjunto do Office 365 de serviços em seu plano, incluindo Skype para negócios.

-   **Skype para a função de administrador de negócios:** Configura Skype for Business para sua organização e é capaz de exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365. Essa função é necessária, mesmo se você implantar apenas equipes.

Como alternativa, você pode atribuir a função a seguir para uma conta de usuário do Office 365 deseja permitir acesso a somente os recursos de relatório.

-   **Relata leitor:** Pode exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365, qualquer relatórios do [pacote de conteúdo do Office 365 adoção](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e relatórios CQD.

Noções básicas sobre os principais conceitos do CQD ajuda a maximizar o impacto que você pode fazer em melhorar a experiência de seus usuários com equipes ou Skype para Business Online.
Recursos adicionais podem ser encontrados no [Apêndice](#other-resources).

## <a name="what-is-quality"></a>Qual é a qualidade?

Ao discutir qualidade em equipes e Skype para os negócios, é importante definir o termo para atingir um entendimento comum. A qualidade, conforme definido aqui, é uma combinação de serviço métricas e experiência do usuário.

![Métricas de serviço são compostas das versões de chamadas ruins proporção, confiabilidade, pontos de extremidade/dispositivos e cliente. Experiência do usuário final é formada pelo percepção do usuário da qualidade de serviço.](media/quality-of-experience-review-guide-image2.png)

_Figura 2: o que há de qualidade?_

### <a name="define-your-target-metrics"></a>Definir seus métricas de destino

Esta seção discute as métricas de serviço principal que usamos para avaliar como serviços apresentem integridade. Continuamente avaliando e orientando os esforços para manter essas métricas abaixo de destino, você vai ajudar a garantir a que qualidade da chamada uniforme e confiável de experiência de seus usuários. Para começar, as metas a seguintes são fornecidas.
Vamos resumem a diferença entre uma rede gerenciada e:

-   Uma rede *gerenciados* pode ser influenciada e controlada pela organização.
    Isso inclui LAN interna, WAN remoto e VPN.

-   Uma rede *não gerenciada* não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de hotel ou aeroporto.

_Tabela 1 - métricas de avaliação de integridade de destino principais_

|               | Qualidade para redes gerenciadas | Confiabilidade para redes gerenciadas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nome de métrica   | % De taxa de chamada de áudio inválida      | Configuração da chamada % de falhas            | Recebimento de chamadas % de falhas |
| Destino da amostra | \<% 3                         | \<% 1                             | \<4%                 |

É importante discutir e definir as metas da sua organização para atender aos seus objetivos de negócios. Idealmente, você deve identificar nestes destinos antes da implantação.

#### <a name="audio-pcr-"></a>% De áudio PCR 

Áudio ruim chamada proporção (PCR) representa a porcentagem geral da organização de chamadas que têm má qualidade de áudio. Essa métrica destina-se para realçar áreas onde sua organização pode se concentrar esforço para ter um impacto mais forte em direção a redução desse valor e aprimorando a experiência do usuário, o motivo pelo qual o foco principal são as redes gerenciadas ao olhar PCR. Os usuários externos são muito importantes, mas difere de investigações em uma base organizacional e de usuário.
Considerar o fornecimento de práticas recomendadas para usuários externos e examine efetuar chamadas externas independentemente do geral da empresa.

#### <a name="call-setup-failures-"></a>Configuração da chamada % de falhas 

Isso representa qualquer sessão de mídia que não pôde ser estabelecida. Devido a gravidade do impacto sobre a experiência do usuário medida aqui, o objetivo é reduzir este valor como como próximos de zero possível. Um valor alto para essa métrica é mais comuns em novas implantações com regras de firewall incompleto do que uma implantação desenvolvido, mas ainda é importante observar regularmente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

#### <a name="call-drop-failures-"></a>Recebimento de chamadas % de falhas 

Isso se aplica a uma carga de trabalho de áudio em que a sessão terminou inesperadamente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

### <a name="service-metrics"></a>Métricas de serviço

Destinos de métricas de serviço consistem em métricas específicas baseados no cliente.

#### <a name="pcr"></a>PCR

A base para determinar se uma chamada foi classificada como ruim é usando a proporção de chamadas ruins (PCR). PCR é formada pelas métricas de rede cinco descritas na tabela a seguir. Para uma chamada para ser classificadas como insatisfatória, apenas uma métrica deve exceder o limite definido. Para obter mais informações sobre o processo de classificação de chamada, consulte [esta postagem de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabela 2 - métricas de serviço de chamadas ruins_

| Métrica                                           | Descrição                                                                                                                                                                                                                                                                                                                                                                  | Experiência do usuário                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tremulação \>30 ms                                   | Esta é a média alteração em atraso entre pacotes sucessivos. Equipes e Skype para negócios podem se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante avisos os efeitos de variação.                                                                                                                         | Os pacotes que chegam em diferentes velocidades causarão voz do alto-falante som robótica.                                                                                       |
| Taxa de perda de pacote \>10% ou 0,1                    | Geralmente, isso é definido como uma porcentagem dos pacotes que são perdidos. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos que têm quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.                                                                                                                               | Os pacotes sendo capitular e não chegada a seu destino pretendido causarão lacunas na mídia, resultando em palavras e sílabas perdidas e entrecortada vídeos e compartilhamento. |
| Tempo de ida e volta \>500 ms                         | Este é o tempo que leva para obter um pacote IP do ponto A ponto b e voltar para a ponto. Esse atraso de propagação de rede é associado à distância física entre os dois pontos e a velocidade da luz e inclui uma sobrecarga adicional tomada por vários dispositivos no caminho de rede.                                                                                  | Os pacotes demorando muito para chegar ao seu destino causam um efeito de walkie-talkie.                                                                                 |
| Média de degradação NMOS \> 1.0                  | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, juntos causado a rede [Pontuação média de opinião](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) para soltar por mais de um ponto. Isso não necessariamente significa que a conexão de rede estiver baixa, mas suficiente problemas ocorreram durante a chamada que qualidade foi reduzida. | Isso é uma combinação de tremulação, perda de pacotes, e — a um grau menor — aumento do tempo de ida e volta. O usuário pode estar apresentando uma combinação desses sintomas.          |
| Taxa média de amostras escondidas \> 7% ou 0,07 | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, causou o cliente auto-restauração a mídia. Uma amostra de áudio escondida é uma técnica costumava suave check-out a transição repentina que geralmente seria causada por pacotes de rede capitular.                                                                                                                | Valores altos indicam que significativo níveis de ocultação perda foram aplicados e resultou em áudio distorcido ou perdido.                                                  |

#### <a name="client-and-device-readiness"></a>Preparação de clientes e dispositivos

Você precisa de uma estratégia sólida de clientes e dispositivos para garantir que os usuários tenham uma experiência de usuário consistente e positivo. Cada estratégia de preparação de unidade de alguns princípios-chave.

##### <a name="client-readiness"></a>Preparação do cliente

Uma estratégia de preparação de cliente forte garante que os usuários estão executando a versão mais recente do cliente ao mesmo tempo aproveitando a melhor experiência possível.
Microsoft rotineiramente patches do Skype para clientes corporativos; garantir que você o mantenha atualizado em seu ambiente é vital para o sucesso geral.

Recomendamos que você não permita que as versões de cliente se encaixam por mais de seis meses. Se você estiver usando o Office Click-to-Run, você estiver já sendo mantidos atualizados pelo serviço. Use o [Relatório de cliente](#determine-client-versions)incluídos, conforme descrito mais adiante neste guia, para ajudá-lo com esse processo. Você também pode aproveitar os relatórios de exemplo de taxa Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de cliente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


##### <a name="device-readiness"></a>Preparação de dispositivo

Sem uma estratégia de única pode afetar a experiência do usuário mais de sua estratégia de preparação de dispositivo. A maioria das organizações são feliz remover dispositivos desnecessários de usuários (por exemplo, telefones de mesa ou outros dispositivos de áudio dedicados), e isso é geralmente uma justificativa comercial de núcleo para alternar para equipes ou Skype para negócios. No entanto, dessas organizações mesmas às vezes hesite para fornecer dispositivos de substituição, mesmo se esses dispositivos são baratos. Moderna laptops e PCs, porém equipados com interna microfone e alto-falante, não são otimizadas para empresarial voz sobre IP (VoIP). Isso geralmente cria uma experiência ruim para todos os participantes, especialmente se o alto-falante está em um ambiente com ruído. Programa de certificação da Microsoft dispositivo garante que, quando um usuário participa de uma chamada telefônica usando qualquer dispositivo certificado para equipes ou Skype for Business, ele produzirá uma experiência que é superior a usar um dispositivo não certificados.

Sempre, recomendamos que equipes e Skype para usuários comerciais usam um fone de ouvido certified ou alto-falante ao participar de uma chamada de voz usando um cliente de desktop.
Para obter mais informações sobre dispositivos de certificados da Microsoft, revise neste [artigo sobre como telefones e dispositivos qualificados](https://technet.microsoft.com/office/dn788944.aspx). Use o [Device Report](#devices-investigations), posteriormente neste guia, para obter ajuda com o gerenciamento de seus dispositivos. Também, você pode usar os relatórios de exemplo de taxa de Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de dispositivo.

### <a name="user-experience"></a>Experiência do usuário

Analisando a experiência do usuário é mais arte do que ciência, porque as métricas coletadas aqui sempre não significa que há um problema com a rede ou serviço, mas em vez disso, eles indicam que o usuário percebe um problema. A Microsoft oferece um mecanismo de pesquisa interno — conhecido como taxa meu chamada (RMC) — para ajudar a estimar a experiência geral do usuário. RMC ajudarão você a responder às seguintes perguntas da perspectiva dos usuários:

-   Saber como usar a solução?

-   É a solução fáceis de usar e intuitiva e oferece suporte a minhas necessidades de comunicação diárias?

-   A solução Ajude-me trabalho?

-   Qual é a minha percepção geral da solução?

-   Posso usar a solução em qualquer ponto no tempo, independentemente de onde estou?

-   É possível configurar e manter uma chamada?

#### <a name="rmc"></a>RMC

RMC compilado no equipes e Skype para negócios e é automaticamente configurado para ser exibida depois que um em cada 10 chamadas ou 10% de todas as chamadas. Este breve pesquisa pede ao usuário classificar a chamada e fornecer um contexto de pouca para por que a qualidade da chamada pode ter sido ruim. Uma classificação de um ou dois é considerada ruim, três ou quatro é bom e cinco é excelente. Embora seja um pouco de um indicador à demora, essa é uma métrica útil para descobrir problemas que métricas de serviço podem perder.

> [!NOTE]
> Até que os usuários são instruídos para responder às pesquisas RMC, oferecendo uma boa indicação além das respostas mal, normalmente volte como predominantemente negativo. A maioria dos usuários responder somente quando a qualidade da chamada é ruim. Dessa forma, seus relatórios RMC podem ser enviesados até o lado ruim mesmo enquanto métricas de serviço estão funcionando bem. 


Você pode usar CQD para reportar sobre as respostas do usuário RMC e relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são abordados em detalhes neste guia. Para obter mais informações sobre o RMC Skype para Business Online e orientações para instruir os usuários a fornecer respostas RMC úteis, consulte esta [postagem de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorias de qualidade

O sucesso do operacionalização de uma implantação de alta qualidade e confiável depende da sua rigor operacionais de construção. Especificamente, prestar bastante atenção em três categorias ilustrado na figura a seguir; Estes são o foco deste guia:

-   **Rede:** Qualidade de áudio com foco na métrica PCR, o uso TCP, sub-redes com e sem fio e identificando o uso de proxies HTTP e VPN.

-   **Pontos de extremidade:** Dispositivos de áudio e a versão do cliente (Skype para negócios apenas).

-   **Gerenciamento de serviços:** Essa categoria consiste em duas seções:

    -   A primeira é responsabilidade da Microsoft para gerenciar e manter as equipes e Skype para serviços corporativos Online.

    -   Segundo são tarefas de que sua organização deve gerenciar para garantir acesso confiável ao serviço, atualizando informações de criação e manutenção de firewalls para novos endereços IP do Office 365 infrastructure for adicionada ao serviço.

![As categorias de qualilty em uma organização: serviço de gerenciamento, pontos de extremidade e a rede.](media/quality-of-experience-review-guide-image3.png)

_Figura 3 - críticas categorias para equipes e Skype para implantação Business Online_

O gráfico a seguir descreve as tarefas que você deve executar para cada categoria. Recomendamos que você execute essas tarefas uma vez por semana, no mínimo.

Na primeira vez que você executar essas tarefas levarão pouco mais do que as iterações subsequentes, pois muitas dessas categorias exigem que você valide suas configurações de implantação. Depois que você tiver obtido o estado desejado atendendo os destinos que você definiu, execução dessas tarefas ajudará você manter esse estado.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Em um mundo primeiro nuvem, você deve executar algumas tarefas de gerenciamento de serviço para manter as experiências do usuário de alta qualidade. Essas tarefas variam de garantir que não há largura de banda suficiente para alcançar o serviço sem links de internet, validando que qualidade de serviço (QoS) de saturação é no lugar em todas as áreas de rede gerenciada, e — finalmente — permanecendo na parte superior [intervalos de IP do Office 365 em firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: qualidade e confiabilidade. Confiabilidade enfoca medindo a capacidade do usuário para fazer chamadas com êxito e permanecem conectadas. Qualidade enfoca a telemetria agregada enviada para equipes e Skype para Business Online pelo cliente do usuário durante e depois que ela for encerrada.

Dado o impacto crítico que confiabilidade tem sobre a experiência do usuário, começar avaliar e investigando dessas métricas antes de começar em qualidade.

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nesta categoria está validando a quais versões do cliente estiver executando o Skype para negócios em compilações da área de trabalho do últimos seis meses para garantir que os usuários estão obtendo o benefício das otimizações contínuas feitas do Skype para o cliente de desktop de negócios. Além disso, isso simplifica as tarefas de gerenciamento de cliente geral e fornece uma experiência de usuário consistente.

A área de importante é quais dispositivos estão predominantes em sua implantação de monitoramento e orientando o uso de dispositivos de certificados para oferecer a melhor experiência de usuário.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


## <a name="using-the-reports"></a>Usando os relatórios

Esta seção descreve os conceitos básicos sobre como trabalhar com CQD. Orientação é fornecida para os seguintes tópicos:

-   Localizando sua ID de Inquilino

-   Relatórios em equipes versus Skype para negócios

-   Primeiro versus segunda classificações

-   Medidas, dimensões e filtros

-   Fluxos de versus chamadas

-   Chamadas boas, ruins e não classificadas

-   Introdução ao CQD

-   Edição de relatórios no CQD

-   Filtragem de relatórios no CQD

Para obter mais aprofundado treinamento e recursos, consulte o [Apêndice](#other-resources).

### <a name="tenant-id"></a>ID do inquilino

Alguns relatórios CQD exigem a inclusão de um filtro para sua ID de Inquilino. Devido a maneira como CQD agrega os dados de telemetria participantes federada é incluída.
Embora isso sejam valioso ao analisar as métricas de chamadas ruins, os relatórios de clientes e dispositivos exigem a filtragem de dados para um locatário específico a serem excluídas telemetria participantes federada. Se você não souber seu ID do inquilino, você pode usar um dos métodos a seguir para localizá-lo.

Requisitos de permissão

-   Função de administrador global

-   Skype para a função de administrador de negócios

#### <a name="azure-ad-portal"></a>Portal do Azure AD

1.  Logon no portal do Microsoft Azure:<https://portal.azure.com>

2.  Selecione o **Azure Active Directory**.

3.  Em **Gerenciar**, selecione **Propriedades**. A ID do inquilino é mostrada na caixa **ID do diretório** .

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Instale o módulo de gerenciamento de serviço do Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra uma janela de comando do Azure PowerShell e execute o seguinte script, inserir suas credenciais do Office 365, quando solicitado:  
    **AzureRmAccount de login**

3.  A ID do inquilino está listada na saída.

#### <a name="skype-for-business-online-admin-center"></a>Skype para negócios Online Admin Center

1.  Ir para<https://portal.office.com>

2.  Entrar com sua conta organizacional do administrador de locatário.

3.  Selecione **Skype para negócios** sob **Centros do administrador**.

4.  A ID do inquilino está listada como **ID da organização** , na página de boas-vindas.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para negócios Online usando o PowerShell

1.  [Conectar-se ao Skype para negócios Online por meio do PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Execute o seguinte comando:  
    **.Tenantid (get-cstenant)**

3.  A ID do inquilino é exibida como um GUID.

### <a name="teams-vs-skype-for-business"></a>As equipes versus Skype para negócios

CQD pode relatar equipes e Skype para telemetria de negócios. No entanto, pode haver ocasiões em que você deseja desenvolver um relatório a ser analisado telemetria de equipes separada do Skype para negócios.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios de resumo a ser analisado apenas equipes ou Skype para negócios, selecione o menu suspenso de **Filtro de produto** da parte superior da tela e selecione o produto desejado.

![Captura de tela do painel de qualidade de chamada refletindo um menu drop-down mostrando a opção de filtragem por carga de trabalho.](media/quality-of-experience-review-guide-image4.png)

_Figura 4 - Selecione um filtro de produto_

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar um relatório detalhado, adicione o filtro **É equipes** ao relatório e defini-la como True ou False. Para obter mais informações, consulte [relatórios de edição](#editing-reports) , mais adiante nesta seção.

![Captura de tela do painel de qualidade de chamada que descrevam o servidor de dados que pode ser adicionado a um relatório detalhado.](media/quality-of-experience-review-guide-image5.png)

_Figura 5 - adicionando um filtro de Teams da Microsoft a um relatório_

### <a name="dimensions-measures-and-filters"></a>Medidas, dimensões e filtros

Uma consulta CQD bem formada contém todas as três dos parâmetros a seguir:

-   **Dimensão:** Como eu desejo os dados de tabela dinâmica.

-   **Medida:** O que eu quero a ser relatado no.

-   **Filtro:** Como deseja reduzir a consulta retornar o conjunto de dados.

Outra maneira de analisar isso é uma dimensão é a função de agrupamento, uma medida é os dados que estou interessado em e um filtro é como eu quiser restringir os resultados para aqueles que são relevantes à minha consulta.

Um exemplo de uma consulta bem formado é "Mostrar-me fluxos ruins [medida] pela sub-rede [Dimension] para construção 6 [filtro]."

Para obter mais informações, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

Para filtros para os relatórios usados nos modelos de CQD, medidas e dimensões, consulte o [Apêndice](#CQD-training).

### <a name="first-vs-second"></a>Primeiro versus segundo 

Muitas das dimensões e medidas em CQD são classificadas como primeira ou segunda.
CQD não usa os campos de chamador/receptor — eles tiverem sido renomeado _primeiro_ e _segundo_ porque há etapas intermediárias entre o chamador e o receptor. A seguinte lógica determina qual ponto de extremidade envolvido no fluxo ou na chamada é rotulado como o primeiro:

-   Primeiro sempre será um ponto de extremidade do servidor (servidor de conferência, o servidor de mediação e assim por diante) se um servidor que está envolvido na chamada ou stream.

-   Em segundo lugar sempre será um ponto de extremidade do cliente, a menos que o stream está entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade são do mesmo tipo, a escolha do qual é a primeira é baseada em ordem interna da categoria de agente de usuário. Isso assegura que a ordenação seja consistente.

Para obter mais informações sobre como determinar o ponto de extremidade de primeiro ou segundo quando eles estão ambos os mesmos, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream versus chamada

Você precisa entender a diferença entre uma chamada e um stream adequadamente escolher quais dimensões ou medidas você vai ser observando em CQD.

**Stream:** Um fluxo existirá apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são exigidos para a comunicação. Fluxos são úteis para analisar os prédios ou redes. Em alguns casos, a chamada e stream são usados no nome de usuário (por exemplo, fluxo de instalação chamada ou chamada ignorados Stream).
Eles ainda são classificados como único fluxos.

**Chamar:** Uma chamada é um agrupamento de todos os fluxos de todos os participantes. Consiste em uma chamada — no mínimo — dois fluxos. Uma única chamada terá dois participantes cada com um mínimo de um stream. As chamadas são úteis para análise de tendências ao longo do tempo.

Para obter orientação adicional sobre a dimensão ou medida fizer referência a uma chamada ou um stream, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada por como BOM, baixa ou não classificados. Vamos falar sobre cada uma em mais detalhes um pouco.

**BOM ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado.
Determinar se uma chamada é bom ou ruim está descrito [neste guia](#pcr).

**Não classificados:** Uma chamada não classificada não contém um conjunto completo de métricas de serviço. Essas são frequentemente chamadas curtas — geralmente menor que 60 segundos — onde não puderam ser computadas médias e um relatório de QoE não foi gerado.

### <a name="access-cqd-online"></a>Acesso CQD Online

Você pode acessar CQD de duas maneiras.

-   Vá para <https://cqd.lync.com>.

-   Vá para **Skype para centro de administração de negócios** \> **Ferramentas**e selecione o link para CQD, conforme mostrado abaixo.

![Captura de tela mostrando "ferramentas" selecionadas no painel de navegação esquerdo e o link para "Skype para Business Online chamada qualidade Dashboard" selecionada.](media/quality-of-experience-review-guide-image6.png)

_Figura 6 – acessando CQD por meio do Skype para centro de administração de negócios_

### <a name="getting-started"></a>Introdução

Quando você procurar primeiro CQD, você verá a página relatórios de resumo. A maioria dos relatórios descritos neste guia são relatórios detalhados personalizados. Para começar a usar os relatórios detalhados, selecione **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

![Captura de tela de depcting o painel de controle de qualidade de chamada os diferentes tipos de relatórios que estão disponíveis.](media/quality-of-experience-review-guide-image7.png)

_Figura 7 - navegando para relatórios detalhados_

A página de relatórios detalhados no CQD se parece com a figura mostrada abaixo.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório.](media/quality-of-experience-review-guide-image8.png)

_Figura 8 - página de relatórios detalhados_

1.  O painel Resumo mostra contexto para o conjunto de relatório que aparece à direita.

2.  Você pode selecionar **Editar** no painel Resumo para definir propriedades de nível de relatório – (incluindo a altura do eixo y).

3.  Navegação estrutural ajuda os usuários a identificar sua localização atual na hierarquia do conjunto de relatório.

4.  Relatórios que têm filhos relatórios são mostrados com um link azul. Selecionando o link, você pode analisar os relatórios de filho.

Aponte para os gráficos de barras e as linhas de tendência para exibir valores detalhados. O relatório que tem o foco mostrará no menu Ação: **Editar**, **Clone**, **Excluir**, **Baixar**e **Exportar árvore de relatório**.

### <a name="editing-reports"></a>Edição de relatórios

Quando você seleciona **Editar** no menu Ação, de um relatório, você vai abrir o Editor de consulta. Cada relatório é feito por uma consulta. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de consulta é uma interface do usuário para edição essas consultas além das opções de exibição para o relatório, como ilustrado na figura a seguir.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório quando o relatório está sendo editado.](media/quality-of-experience-review-guide-image9.png)

_Figura 9 - Editor de relatório_

1.  Você escolher medidas, dimensões e filtros de painel à esquerda. Apontando para um valor existente exibe um botão Fechar (**X**) que você pode optar por remover o valor.

    1.  Selecionando a dimensão ou medida, você pode alterar o título editando o campo **cargo** . Você também pode alterar a ordem selecionando o azul aumentar ou diminuir setas no painel superior.

    2.  Selecionando (**+**) ao lado de um título abre a caixa de diálogo para adicionar uma nova dimensão, uma medida ou um filtro.

    3.  Digite as primeiras letras da dimensão, medida ou filtro no **encontrar um** campo para filtrar a lista para facilitar a pesquisa.

2.  O painel superior mostra as opções de personalização do gráfico.

3.  O Editor de consulta mostra uma visualização do relatório.

4.  Use a caixa **Editar** na parte inferior da tela para criar ou editar uma descrição detalhada do relatório.

### <a name="filtering-reports"></a>Filtragem de relatórios

Os modelos fornecidos inclui várias consultas integradas e filtros do relatório. As seções a seguir descrevem os filtros mais comuns usados em todo os modelos.

#### <a name="cqd-filter"></a>Filtro CQD

Você pode usar o filtro CQD ou o filtro de URL, filtrar temporariamente cada consulta de relatório. O filtro de CQD mais comuns que você utilizará é filtrar relatórios a serem excluídas telemetria participantes federada. Recomendamos que você crie um indicador esse filtro para que ele se torna o modo de exibição padrão. Excluindo dados federados de relatórios CQD é útil quando você estiver correção prédios gerenciados ou redes onde os dados federados podem influenciar seu relatório.

Para implementar um filtro CQD, na barra de endereço do navegador, acrescente o seguinte ao final da URL:

/Filter/ [AllStreams]. [Id do inquilino segundo] \|[Sua ID do INQUILINO aqui]

**Exemplo:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Id do inquilino segundo] \|[TENANTID] & locatário = TENANTID

> [!NOTE]
> O exemplo de URL acima destina-se somente a representação visual. Use o link CQD padrão de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta são implementados usando o Editor de relatório. Esses filtros são usados para reduzir o número de registros retornados por CQD, minimizando o tamanho de geral do relatório. Isso é especialmente útil para filtragem de redes não gerenciados.
Os filtros abaixo usam expressões regulares (RegEx).

_Tabela 3 - filtros de consulta_

| Filtro               | Descrição          | Exemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores em branco         | Alguns filtros não tem a opção para filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e definir o filtro é igual a ou não for igual a, dependendo das suas necessidades.                                                                                                                             | Construção do segundo nome \< \> \^ \\s\*\$                       |
| Populares sub-redes residencial | Sem um arquivo de construção válido para separar gerenciada de redes não gerenciados, redes domésticas terão obter incluídos nos relatórios. Essas sub-redes residencial estão fora do escopo do controle de TI e podem ser rapidamente excluídos de um relatório. Populares sub-redes residencial, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Inside versus fora   | Usado para filtrar um relatório para (interna) gerenciado ou (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.                                                                                                                                                                                | Segundo dentro Corp = dentro                               |

#### <a name="report-filters"></a>Filtros do relatório

Filtros do relatório são implementados adicionando um filtro ao relatório renderizado tanto no relatório Editor ou diretamente ao relatório. Os filtros de relatórios a seguir são usados em todo o modelo.

_Tabela 4 - filtro de relatório_

| Filtro     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Comece com o ano primeiro e, em seguida, mês. | 10 de 2017                           |
| Alfabético | Filtra quaisquer caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos os caracteres numéricos.    | [0-9]                             |
| Porcentagem | Filtra uma porcentagem.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar os modelos CQD

Este guia inclui [dois modelos CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Esses modelos aceleram seu uso de CQD e fornecem a você uma oportunidade para aproveitar rapidamente os recursos do CQD para tornar um impacto sobre equipes ou do Skype dos usuários para a experiência de negócios. O modelo de todas as redes, porém otimizado para funcionar com um edifício pode ser usado o arquivo de dados, enquanto você trabalha em direção a coleta e carregamento de informações de construção em CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) em CQD Online**

1.  Vá para <https://cqd.lync.com>.

2.  Autentica usando suas credenciais administrativas do Office 365.

> [!NOTE]
> Você deve ter o Office 365 Global administrador Skype para administrador de negócios ou função de leitores de relatório acessar CQD. 


3.  Selecione o menu de **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

4.  No painel Resumo, selecione **Importar**. Vá para o CQDX salvo local, selecione o modelo CQDX e selecione **Abrir**.

5.  Depois que o modelo for carregado, uma janela pop-up será exibida a mensagem "a importação de relatório teve êxito." Selecione **Okey.**

![Captura de tela de uma janela pop-up que notifica o usuário se o modelo foi importado com êxito.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita as etapas 4 e 5 para o segundo modelo CQD.

> [!NOTE]
> Os modelos CQD são importados por usuário. Se outros usuários precisarem usar o relatório, eles devem entrar e importar os modelos em sua instância CQD. 


## <a name="building-mapping"></a>Mapeamento de construção

Em um equipes ou Skype para implantação Business Online, todos os clientes são externos.
Que tem a implicação que, por padrão, todos os clientes são indicados como fora em CQD Online, independentemente de se o cliente foi conectado em uma rede corporativa interna.

Quando você trabalha com a qualidade de chamada, você precisa saber o local de um cliente e se ele foi conectado a uma rede que você pode gerenciar ou de uma rede não é possível gerenciar — a pressuposição sendo que você só pode melhorar redes você pode gerenciar.
Carregando informações de construção e rede para CQD Online, você deve habilitar CQD determinar se um cliente foi conectado a uma rede interna de corporativo/gerenciados ou a uma rede externa/não gerenciados.

### <a name="building-data-file-structure"></a>Estrutura do arquivo de dados de construção

O formato do arquivo de dados que você carrega deve atender aos seguintes requisitos para passar a verificação de validação antes de carregar.

-   O arquivo deve ser um arquivo TSV, o que significa que, para cada linha, cada coluna é separada por um caractere de tabulação, ou um arquivo CSV no qual cada coluna é separada por uma vírgula.

-   O arquivo não pode ser maior do que 50 MB.

-   O conteúdo dos dados de arquivo *não deve incluir cabeçalhos de tabela*. Em outras palavras, a primeira linha do arquivo de dados deve ser dados reais, e não os títulos de coluna, como "Rede".

-   Para cada coluna, o tipo de dados só pode ser cadeia de caracteres, número ou Bool. Se o tipo de dados for um número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.

-   Para cada coluna, se o tipo de dados é a cadeia de caracteres, os dados podem estar vazios (mas ainda devem ser separados por um delimitador apropriado, que é um caractere de tabulação ou por vírgula). Isso simplesmente atribui esse campo um valor de cadeia de caracteres vazia.

-   Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados descrito na tabela a seguir, e as colunas devem estar na ordem listada na tabela.

_Tabela 5 - Criando a estrutura do arquivo_

| Nome da coluna        | Tipo de dados | Exemplo                   | Orientação    |
|--------------------|-----------|---------------------------|-------------|
| Rede            | Cadeia de caracteres    | 192.168.1.0               | Obrigatório    |
| NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-mar-1 | Necessário\*  |
| NetworkRange       | Número    | 26                        | Obrigatório    |
| BuildingName       | Cadeia de caracteres    | SEATTLE-MAR-1             | Necessário\*  |
| OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional    |
| BuildingType       | Cadeia de caracteres    | Terminação de IT            | Opcional    |
| BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional    |
| Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado |
| CEP            | Cadeia de caracteres    | 98001                     | Recomendado |
| País            | Cadeia de caracteres    | CONOSCO                        | Recomendado |
| Estado              | Cadeia de caracteres    | WA                        | Recomendado |
| Região             | Cadeia de caracteres    | MSUS                      | Recomendado |
| InsideCorp         | Bool      | 1                         | Obrigatório    |
| ExpressRoute       | Bool      | 0                         | Obrigatório    |

\*Embora não seja necessário por CQD, os modelos estão configurados para exibir a criação e a rede nome.

#### <a name="supernetting"></a>Combinação de redes

Você pode usar a combinação de redes, geralmente chamado de roteamento entre domínios sem classificação (CIDR), no lugar de definição de cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR. Combinação de redes é suportada, mas não recomendamos utilizá-lo.

Por exemplo, a construção de marketing da Contoso é composta das sub-redes abaixo:

-   10.1.0.0/24 – primeiro andar

-   10.1.1.0/24 – 2º andar

-   10.1.2.0/24 – 3º andar

-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR — neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0

-   Intervalo de rede = 22

Aqui estão algumas coisas a considerar antes de implementar a combinação de redes:

-   Combinação de redes demora menos tempo desde o início, mas que se refere ao custo reduzir o aperfeiçoamento em termos de seus dados. Digamos que não há uma sub-rede de envolvendo do problema de qualidade 200.1.2.0. Se você implementou a combinação de redes, você não saberá onde a sub-rede está localizada no edifício ou tipo de rede que está (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes de um edifício e carregado informações de local andar, você poderá ver essa distinção.

-   É importante garantir que o endereço de supernetted/CIDR está correto e se não está capturando sub-redes indesejadas.

-   Combinação de redes pode ser usada em um mapeamento de construção com máscara de 8 bits para 28 bits.

-   Ele é bastante comum para encontrar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outras pessoas, esse é o esquema de endereço IP de um escritório de satélite. Se sua organização tem escritórios que usam essa configuração, não incluí-lo em seu arquivo de construção conforme é difícil distinguir entre redes domésticas e internos usando sub-redes comuns.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todas as novas criar carregamentos de arquivos de dados será verificado para todos os intervalos de sobreposição. Se você carregou anteriormente um arquivo de construção, você deve baixar o arquivo atual e carregá-la novamente para identificar qualquer sobreposições e corrigir o problema. Qualquer sobreposição nos arquivos carregados anteriormente pode resultar em mapeamentos de sub-redes aos prédios nos relatórios errados. 


#### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Office 365 — que é onde os dados CQD originados de — inclui um sinalizador VPN. No entanto, esse sinalizador depende de relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN registrado é um adaptador de acesso remoto. Nem todos os fornecedores VPN adequadamente registre os adaptadores de acesso remoto. Dessa forma, você não poderá usar os filtros de consulta VPN internos. Há duas abordagens para acomodar sub-redes VPN no edifício arquivo de informações.

-   Defina um **Nome de rede** usando o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma sub-rede VPN](media/quality-of-experience-review-guide-image10.png)

_Figura 10 - VPN usando o nome de rede_

-   Defina um **Nome de construção** usando-se o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma definição de construção que consiste em uma sub-rede VPN.](media/quality-of-experience-review-guide-image11.png)

_Figura 11 - VPN usando o nome do edifício_

> [!IMPORTANT]
> Determinadas implementações de VPN com precisão não relatam informações de sub-rede. Se isso ocorrer em seu relatório, que é recomendável que, quando você adiciona uma sub-rede VPN para o arquivo de construção, em vez de uma entrada para a sub-rede, adicione entradas separadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você tem 253 linhas, com uma linha para cada endereço de 172.16.18.1/32 por meio de 172.16.18.254/32, inclusive.


> [!NOTE]
> Conexões VPN são conhecidas por cometem erros conforme com fio quando a conexão de internet subjacente está na identificação de conexão de rede sem fio. Ao olhar qualidade em conexões VPN, você não pode assumir que o tipo de conexão foi identificado com precisão.

### <a name="uploading-building-information"></a>Carregar informações de construção

O painel de relatórios de resumo de CQD inclui uma página de **Carregamento de dados de Inquilino** , acessada selecionando a marca de link de **Carregamento de dados de Inquilino** no canto superior direito (procure o ícone de engrenagem). Esta página é usada para os administradores para carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeando cada ponto de acesso sem fio e seu endereço MAC e assim por diante.

1.  Vá para CQD Online navegando até <https://cqd.lync.com>.

2.  Selecione o ícone de engrenagem no canto superior direito e escolha o **Carregamento de dados de Inquilino** na página **Relatórios de resumo** .

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que é exibido enquanto dados está sendo carregados.](media/quality-of-experience-review-guide-image12.png)

_Figura 12 - menu de carregamento de dados de Inquilino_

1.  Como alternativa, se essa for a primeira vez em que visitando CQD, você será solicitado para carregar dados de construção. Você pode selecionar **Carregar Agora** para navegar rapidamente para a página de **Carregamento de dados de Inquilino** .

![Captura de tela de um banner no painel de qualidade de chamada que notifica o usuário para carregar dados de construção.](media/quality-of-experience-review-guide-image13.png)

_Figura 13 - Criando banner de carregamento de dados_

1.  Na página de **Carregamento de dados de Inquilino** , selecione **Procurar** para escolher um arquivo de dados.

2.  Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, especifique uma data de término.

3.  Depois de selecionar a **Data de início**, selecione **carregar** para carregar o arquivo para o CQD. <br><br>Antes do arquivo for carregado, ele será validado. Se a validação falhar, uma mensagem de erro é exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que descreve uma mensagem de erro ao importar dados de construção.](media/quality-of-experience-review-guide-image14.png)

_Figura 14: Criando o erro de carregamento de dados_

4.  Se nenhum erro ocorrer durante a validação, o carregamento de arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregados na **Minhas carregamentos de** tabela, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já tiver carregado um arquivo de construção e precisa para adicionar as sub-redes que podem ter sido perdidas ou excluídos, modifique o arquivo original adicionando novas sub-redes, remova o arquivo atual e reenvie o arquivo recentemente editado. Pode haver construção ativa apenas um arquivo de dados em CQD. 

### <a name="missing-subnets"></a>Sub-redes ausentes

Após carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre é o caso; Normalmente, as sub-redes alguns são perdidas. Esta seção aborda como validar as redes ausentes.

Navegue até a página de **Relatórios detalhados** no CQD Online e navegue até o **Relatório de sub-rede ausentes** incluídas nos modelos CQD. Isso apresenta todas as sub-redes com 10 ou mais áudio fluxos que não são definidos no edifício arquivo de dados. Certifique-se de que não há nenhuma redes gerenciadas nessa lista. Se não existirem sub-redes, atualize o edifício original do arquivo de dados e reenvie a CQD.

> [!IMPORTANT]
> Você precisará adicionar sua ID de Inquilino como um filtro de consulta para a **Segunda ID do inquilino** para este relatório para filtrar o relatório para exibir somente os dados de inquilinos da sua organização. Caso contrário, o relatório mostrará sub-redes federados.

> [!NOTE] 
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.                                                  |

![Relatório mostrando as sub-redes não são incluídos no arquivo de dados de construção CQD que mostram o uso.](media/quality-of-experience-review-guide-image15.png)

_Figura 15 - ausente relatório de construção_

## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para aprimorar a qualidade é para avaliar o estado de confiabilidade de áudio em toda a organização. Confiabilidade de áudio, pois é vital para uma experiência de usuário positivo iniciamos com os dois componentes que medem confiabilidade:

1.  **Falhas de instalação de chamada:** Sessão não pôde ser estabelecida.

2.  **Falhas de recebimento de chamadas:** Sessão foi estabelecida e finalizada inesperadamente

Ao longo desta seção, abordaremos métodos para ambas as áreas de investigar.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações.


### <a name="call-setup"></a>Configuração da chamada

Priorize remediando falhas de instalação chamada nessa área em primeiro lugar, pois essas falhas possuem um impacto negativo significativo na experiência do usuário.

Começar a investigação avaliando a porcentagem de falhas de instalação chamada geral para a organização e, em seguida, priorizar áreas de investigação com base na porcentagem mais alta, criação ou da rede.

#### <a name="call-setup-failures-overall"></a>Falhas de instalação gerais de chamadas

Este relatório de gráfico exibe a quantidade total de chamada bem sucedida, configurar e falhas de instalação de chamadas ao longo do tempo. Aponte para qualquer uma das colunas para exibir seus valores individuais, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico que mostra o percentual de falha na instalação do fluxo de chamadas de áudio](media/quality-of-experience-review-guide-image16.png)

_Figura 16 - confiabilidade de áudio - falhas de instalação de fluxo de chamada_

##### <a name="analysis"></a>Análise

Este relatório exibe o uso da instalação chamada de áudio e falhas de sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas e determinar sua próxima ação:

1.  Qual é a porcentagem de falha de instalação chamada total para o mês atual?

2.  É a porcentagem de falha de instalação chamada total abaixo ou acima a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório informará a história da frequência suas configurações gerais de chamada estão falhando em toda a organização.

Independentemente das respostas anteriores, reserve um tempo para investigar maior usando os sub-relatórios incluídos para procurar por qualquer prédios individuais ou redes que possam precisar de remediação. Embora a taxa de falha geral pode estar abaixo na métrica de destino, geralmente as taxas de falha para uma ou mais redes ou prédios são acima na métrica e precisam remediação.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Falhas de instalação de chamada Construindo e sub-rede 

Este relatório de tabela é usado para descobrir e isolar qualquer prédios ou redes que precisam de correção.

> [!NOTE]
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.


![Relate que razões de falha de instalação de chamada de listas, organizados construindo, a rede e a sub-rede por mês.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - falhas de configuração de áudio, criando ou sub-rede_

##### <a name="remediation"></a>Remediação 

Concentre os esforços de remediação em prédios ou sub-redes que tenham o maior volume de falhas em primeiro lugar, porque isso maximizar o impacto sobre a experiência do usuário e ajudam a reduzir rapidamente as falhas de instalação chamada organizacionais.
A tabela a seguir lista as duas razões para falhas de instalação chamada conforme relatado pelo CQD.

_Tabela 6 – razões para falhas de instalação chamada_

| Chamar o motivo de falhas de instalação                       | Causa comum                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Regra de isenção de inspeção de pacotes de profundidade de firmware de ausentes | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida devido às regras de inspeção de pacotes de profundidade. Isso é provável devido às regras de firewall não está sendo configuradas corretamente. Neste caso o handshake TCP foi bem-sucedida, mas o handshake SSL não especificou.               |
| Regra de exceção do bloco de IP de firmware de ausentes               | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida com a rede do Office 365. Isso pode ser devido às regras de firewall ou proxy não está sendo configuradas corretamente para permitir acesso aos endereços IP e portas usadas para equipes e Skype para tráfego de negócios. |

Agora como começar sua remediação, é possível focar seus esforços em um edifício ou sub-rede. Conforme mostra a tabela anterior, esses problemas são devido às configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de remediação.

_Tabela 7 - próximas etapas para a chamada de correção de falha de instalação_

| Remediação           | Orientação     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewalls | Trabalhar com a equipe de rede e verifique se a sua configuração de firewalls contra [a lista de endereços IP do Office 365](https://aka.ms/o365ips). Verifique se as portas e [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) são incluídas nas regras de firewall. Verifique se que as portas TCP e UDP necessárias sejam abertas no firewall. Mídia prefere UDP sobre TCP. TCP é considerado um protocolo de failback.<br><ul><li>**TCP:** a porta 443</li><li>**UDP:** portas 3478 – 3481</li><ul> |
| Verifique se                | Utilize a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar a conectividade do edifício afetado ou sub-rede usando a função de verificação de conectividade.    |


### <a name="call-drop"></a>Recebimento de chamadas

Ao contrário de falhas de instalação chamada, não há nenhum código de motivo para indicar por que a chamada abandonada falhas ocorreu, o que torna difícil isolar uma causa raiz específica. Para melhor triagem chamadas capitular, use uma abordagem deduzida. Correção de quaisquer áreas de interesse para áudio, os clientes de aplicação de patch e orientando o uso de dispositivos de certificados para equipes e Skype for Business, você esperaria falhas de chamada queda para recusar.

#### <a name="call-drop-failures-overall"></a>Geral de falhas de recebimento de chamadas

Este relatório de gráfico exibe a quantidade total de fluxos de áudio, fluxos de áudio total ignorados, e a porcentagem de queda de fluxo total. Aponte para qualquer uma das colunas para exibir seus valores, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico mostrando a porcentagem de queda de fluxos de áudio de chamada](media/quality-of-experience-review-guide-image18.png)

_Figura 18 - chamada Total queda percentual de falha_

##### <a name="analysis"></a>Análise

Este relatório de gráfico exibe a falhas e o uso da sua organização ao longo do tempo relacionado ao chamar quedas. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a chamada atual de total queda porcentagem?

2.  É a porcentagem do total de depósito abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório podem saber a história da frequência suas geral quedas de chamada estão ocorrendo em toda a organização.

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. Embora a taxa geral de recebimento pode estar abaixo na métrica de destino, muitas vezes a taxa de recebimento de um ou mais redes ou prédios estiver acima na métrica e precisa remediação.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Falhas de recebimento de chamadas pela criação ou sub-rede

Falhas neste relatório de tabela indicam que a chamada foi interrompida inesperadamente e resultou em uma experiência de usuário negativo. Existem dois relatórios de tabela incluídos no modelo, um para investigar a conferência e outro para duas partes.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.


![Relatório que relaciona o número e a porcentagem de queda de chamadas, organizadas por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image19.png)

_Figura 19 – a chamada de áudio queda de falhas pela criação ou sub-rede_

##### <a name="remediation"></a>Remediação

Usando o relatório de tabela anterior, você pode isolar agora "pontos de acesso" na rede gerenciada onde quedas de chamada ocorrerem acima a métrica destino definida. Concentre os esforços de remediação em prédios ou redes que possuem a contagem de fluxo total mais alta primeiro, para tornar o maior impacto.

Causas comuns de quedas de chamada:

-   Saída de rede ou internet em provisionado

-   Nenhum QoS configurado em redes restritas

-   Versões mais antigas do cliente

-   Comportamento do usuário

Depois que você descobrir os pontos de acesso, você pode aproveitar a [Chamada análise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar ainda mais usuários em que construção para problemas específicos. Análise de chamada contém dados PII e pode ser útil para isolar ainda mais os motivos possíveis para a cai de chamada.

Independentemente da sua próxima etapa, é uma boa prática para notificar a helpdesk que foi descoberto um problema com os prédios específicos ou sub-redes. Dessa forma, rapidamente eles podem responder às chamadas recebidas e triagem usuários com mais eficiência. Usuários sinalizados, em seguida, podem ser informados volta para a equipe de engenharia para uma investigação detalhada.

A tabela a seguir lista alguns métodos comuns para gerenciar e remediar quedas de chamada.

_A tabela 9 - próximas etapas para chamada drop remediação_

| Remediação                              | Orientação     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rede/internet                         | Agora que você sabe qual construção é afetada, trabalhe com a equipe de rede para monitorar a largura de banda em que construção para determinar se há problemas com excesso. Se o problema for detectado estar relacionado ao congestionamento da rede, considere o aumento de largura de banda para essa construção. <br><br>**QoS:** Se o aumento da largura de banda é impossível ou caro, considere a implementação de QoS. Isso garantirá a pacotes de mídia na rede gerenciada são priorizados acima tráfego de mídia não. Como alternativa, se não houver nenhuma evidência clara que largura de banda é o responsável, considere estas soluções:<br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação. <br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra os [requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clientes (Skype para negócios apenas Online) | Alguns clientes mais antigos possuem conhecidos, documentados problemas com confiabilidade de mídia. Revise os relatórios de análise de chamada de vários usuários afetados ou crie um relatório de tabela de versão do cliente personalizado no CQD filtrado específicos prédios ou sub-redes com medida de % do Total de chamadas queda de falha. Essas informações ajudarão você a entender se existe uma relação entre quedas de chamada na que edifício específico e uma versão específica do cliente.                                                                                                                                                              |
| Dispositivos                                  | A maioria das falhas de dispositivo são devido ao uso de dispositivos que não são certificados para equipes ou Skype para negócios. Falhas normalmente assumem a forma do integrada de alto-falantes ou microfones que estão sendo usados ou combinações de earbud/microfone estão conectadas à tomada de áudio de 3,5 mm em um dispositivo. Recomendação de atual da Microsoft é que todos os usuários que estão enfrentando chamar quedas — ou ruins chama em geral — e estão usar dispositivos integrados ou drivers deve ser provisionado um [certificado headset ou viva-voz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamento do usuário                            | Se achar que nem rede, dispositivos ou clientes são o problema, considere o envolvimento do [Meu Advisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de adoção de usuário para instruir os usuários como práticas ingressar e sair de reuniões. As equipes de uma forma mais inteligente e Skype usuário produzirá uma melhor experiência de usuário para todos os participantes da reunião. Um usuário que coloca seus laptops em suspensão (fechando a tampa) sem sair da reunião será classificado como um depósito chamada inesperada.     |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade de áudio entre a implantação é investigar áudio ruim chamada proporção (PCR), TCP e uso de proxy. É importante lembrar que os dados CQD não fornecem uma causa raiz específica, mas fornece em vez disso, com áreas de problema provavelmente iniciar uma conversa de colaboração com as equipes apropriadas para atividades de correção.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="investigate-call-quality"></a>Investigar a qualidade da chamada

A porcentagem PCR geral é usada principalmente para indicar se a organização é reunião destinos de métricas de áudio definidos. É importante observar que, mesmo se a porcentagem geral estiver dentro de destino, alguns sub-redes ou prédios talvez não cumprir os objetivos definidos e, portanto, precisa as investigações. Por exemplo, se a porcentagem PCR áudio organizacional for % 3 em dezembro, que atende o destino de amostra, prédios específicos pode ainda ser tendo experiências ruins, dependendo da distribuição de que % 3.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentagem de chamadas ruins organizacional geral

Para avaliar a porcentagem geral de chamadas de baixa para a organização usar o relatório de gráfico de qualidade geral.

![Captura de tela de um gráfico mostrando a porcentagem de chamadas de baixa qualidade](media/quality-of-experience-review-guide-image20.png)

_Figura 20 – qualidade de áudio - geral_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe PCR e o uso da sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que podem precisar de mais investigação. Embora a PCR geral pode estar abaixo na métrica de destino, muitas vezes PCR para um ou mais prédios ou redes estiver acima na métrica e precisa ainda mais investigação.

#### <a name="audio-quality-overall"></a>Qualidade de áudio geral

Há duas árvores de relatório incluídas nos modelos de qualidade de áudio, um para investigar a conferência e outro para chamadas de duas partes. Para fins de remediação de qualidade, o processo de investigação é a mesma, portanto focaremos aqui na conferência. Melhorias na qualidade de conferência também positiva afetará a qualidade das chamadas de duas partes. Relatórios também são incluídos para exibir a qualidade de áudio para conferências e duas partes por com fio e Wi-Fi.

> [!NOTE]
> Investigar chamadas de baixa de duas partes é semelhante ao investigando chamadas em conferência. A tarefa é identificar prédios ou sub-redes que tenham a qualidade inferior para validar se houver um padrão de chamadas ruins com outra construção ou sub-rede. 

![Captura de tela da qualidade de áudio - relatório de conferência no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image21.png)

_Figura 21 – qualidade de áudio - conferência_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe a conferência da sua organização ou uso de dois participantes e PCR ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É PCR pior ou melhor do que o mês anterior?

4.  É a tendência PCR aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que talvez seja necessário investigação. Embora a PCR geral pode estar abaixo na métrica de destino, geralmente PCR para um ou mais prédios ou redes estiver acima na métrica e precisa remediação.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Fluxo de áudio ruim Construindo e sub-rede

Este relatório de tabela oferece compreensão adicional sobre o que contribuíram para as chamadas sendo classificada como pobre e ajuda a isolar os pontos de acesso da rede gerenciada.

Os detalhes de conexão distingue com fio e Wi-Fi e inclui as medições de tempo de ida e volta (tempo de resposta), perda de pacote e Tremulação. Um relatório semelhante também existe sob os relatórios de duas partes e é usado para isolar as chamadas de duas partes em sua rede gerenciada.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão. 

> [!TIP]
> Redes domésticas comuns são difíceis de triagem devido ao seu uso amplo. Foi adicionado um relatório separado que usa o IP do firewall para o modelo de todas as redes para auxiliar com escritórios remediando que usam redes comuns.

![Relatório que lista os tipos de conexão, tipos de transporte e PCR maior que 3%, juntamente com várias finalidades de baixa qualidade organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image22.png)

_Figura 22 - resumo de fluxo de áudio ruim, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Concentrar os esforços de remediação em prédios ou redes que possuem o maior volume de fluxos de áudio, pois isso maximizar o impacto e ajudar a melhorar o usuário experimentam rapidamente. Use a tremulação, perda de pacotes e medidas de tempo de resposta para compreender o que está contribuindo para a qualidade da chamada ruim. É possível para ter mais de um problema:

-   **Tremulação:** Pacotes de mídia chegam ao velocidades diferentes, o que faz com que um alto-falante som robótica.

-   **Perda de pacotes:** Pacotes de mídia estão sendo eliminados, que cria o efeito das palavras ou sílabas faltando.

-   **Tempo de resposta:** Pacotes de mídia estão demorando muito tempo para chegar ao seu destino, que cria um efeito de walkie-talkie.

Embora nenhuma fonte única de veracidade contas para o que pode causar uma chamada de baixa, vários métodos comuns podem ajudá-lo a lidar com problemas de rede.

Para auxiliar sua investigação sobre problemas de qualidade, você pode aproveitar a [Análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Com a análise de chamada, você pode examinar uma conferência específica ou relatório de chamada detalhada dos usuários. Este relatório conterá os dados PII e é útil quando tentar distinguir um motivo para falhas. Quando você souber qual edifício é afetado, rastreamento de usuários em que a construção deve ser simples.

Não se esqueça de informar a helpdesk que essas redes estão enfrentando problemas de qualidade, para que possam rapidamente triagem e responder às chamadas recebidas.

_A tabela 9 - comuns Contribuidores PCR alta_

| Remediação                              | Orientação       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Uma rede com uso excessivo ou em provisionado pode causar problemas com a qualidade de mídia. Trabalho com a equipe de rede para determinar se as conexões de rede do usuário até a saída de internet apontam tem largura de banda suficiente para oferecer suporte a mídia. **Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação.<br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. Essa ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra as de desempenho do Microsoft [requisitos](https://aka.ms/performancerequirements).<br><ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Qualidade de serviço (QoS)                 | QoS é um método comprovado para ajudar a priorizar pacotes em uma rede para garantir que eles cheguem a seu destino intacto e no tempo. Considere a implementação de QoS em toda a organização para maximizar a qualidade da experiência do usuário onde a largura de banda é limitada ou restrita. QoS ajudarão a solucionar problemas normalmente associados a altos níveis de perda de pacotes, e — a um grau menor — tempos de tremulação e de ida e volta. <br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi pode ter um impacto significativo sobre a qualidade da chamada. Design de Wi-Fi não terá normalmente em consideração os requisitos de rede para serviços de VoIP e, geralmente, é uma fonte de baixa qualidade. **QoS:** Redes sem fio modernos devem oferecer suporte a vários dispositivos. Esses dispositivos competem por largura de banda e podem causar problemas de qualidade para serviços de VoIP onde estão vitais velocidade e a latência. Consulte seu fornecedor de sem fio para obter informações específicas e considere a implementação de QoS em sua rede sem fio priorizar Skype para negócios e equipes de mídia. **Densidade AP:** Pontos de acesso (pontos de acesso) podem ser muito distantes ou não em um local ideal. Para minimizar a interferência potencial, coloque extras pontos de acesso em salas de conferência e em locais que não são obstruídos por paredes ou outros objetos. **2,4 GHz versus 5 GHz:** 5 GHz fornece menos interferência de plano de fundo e as velocidades maiores e devem ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não entrar na paredes tão facilmente. Examine seu layout de construção para determinar qual frequência você pode depender para a conexão recomendada. **Intensidade do sinal:** Em geral, medido em dBm (taxa de alimentação em decibéis), mede a intensidade do sinal sem fio. Depois que um dispositivo está conectado a um ponto de acesso, ele não quer permitir que vá facilmente. Como o dispositivo se move para fora do ponto de acesso, a intensidade do sinal cai para um ponto que induz uma conexão ruim, mesmo que a outra, quanto mais perto AP está disponível. Se possível, trabalhe com seu fornecedor de AP para garantir que os pontos de acesso estão configurados para descartar um dispositivo quando a intensidade do sinal fica abaixo de um nível aceitável. Isso garantirá que o dispositivo não congele um PA fraca. Isso é uma boa solução quando você não pode adicionar facilmente mais pontos de acesso. **Driver wireless:** Quando tudo mais falhar, certifique-se de que os drivers sem fio estão atualizados. Isso ajudará a atenuar qualquer experiência de usuário ruim relacionada a um driver desatualizado. |
| Dispositivo de rede                           | Organizações maiores podem ter centenas de dispositivos afastadas através da rede. Trabalho com a sua equipe de rede para garantir que os dispositivos de rede do usuário para a internet são mantidos e atualizados.     |
| VPN                                      | Ele foi bem documentado que aparelhos VPN tradicionalmente não são projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferido para áudio) e contam com apenas TCP. Considere a implementação de uma [solução de divisão de túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ajudar a reduzir a VPN como uma fonte de baixa qualidade.        |
| Clientes (Skype para negócios apenas Online) | Clientes mais antigos são conhecidos por causar problemas com a mídia. Certifique-se de que os clientes estão sendo patch dentro de seis meses após o lançamento. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de cliente e deploy [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | O uso de [dispositivos de otimizado](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pode ajudar a melhorar significativamente a experiência do usuário. Com todas as coisas sendo igual, dispositivos otimizados foram projetados para maximizar a experiência do usuário com equipes e Skype para negócios e produzir qualidade superior. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar sessões de áudio de TCP

TCP é considerado um transporte failback e não o transporte principal que você deseja para a mídia em tempo real. Isso é um transporte failback é devido à natureza do TCP com informações de estado. Por exemplo, se uma chamada for feita em uma rede latente e pacotes de mídia estão atrasados, em seguida, os pacotes de alguns segundos atrás — que não são mais úteis — competem por largura de banda chegar ao destinatário, que pode tornar um pior situação ruim. Isso torna o stitch de correção de áudio e áudio Alongar, resultando em artefatos audíveis geralmente na forma de tremulação.

Os relatórios nesta seção não fizer uma distinção entre chamadas boas e ruins. Visto que UDP é o preferido, os relatórios procuram o uso de TCP para áudio. Isso é principalmente causado pelas regras de firewall incompleta. Para obter mais informações sobre regras de firewall para equipes e Skype para Business Online, consulte [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Fluxos de áudio com o uso TCP geral

Este relatório indica o uso geral de TCP para áudio nos últimos sete meses, conforme mostrado abaixo.

Todos os relatórios mais nesta seção abordará estreitando pressionada prédios específicos e sub-redes onde o TCP é usado com mais frequência. Mais sub-relatórios romper o uso TCP por conferência e chamadas de duas partes.

![Captura de tela de um gráfico mostrando o número de fluxos de áudio de TCP por mês](media/quality-of-experience-review-guide-image23.png)

_Figura 23 – fluxos de áudio com o uso TCP_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe o uso TCP geral da sua organização. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é o volume total de chamadas TCP para o mês atual?

2.  É melhor do que o mês anterior ou de pior?

3.  É a tendência de uso do TCP aumentando, steady, ou diminuindo?

Se notar que a tendência de uso do TCP está aumentando ou acima de utilização monthly normal, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. O ideal é que você deseja, no mínimo com base em TCP sessões de áudio possível na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Este relatório de tabela identifica o volume de TCP versus relatórios sobre o mês mais recente para conferências de áudio, vídeo e vídeo-based (VBSS) de compartilhamento de tela de uso do UDP.

![Relatório mostrando o volume de TCP versus fluxos de conferência UDP, com PCR mostrado na comparação](media/quality-of-experience-review-guide-image24.png)

_Figura 24 – TCP versus UDP - conferência_

##### <a name="analysis"></a>Análise

Embora você deseja o uso TCP ao ser tão baixa quanto possível, talvez você veja um pouco de uso TCP em uma implantação do contrário íntegro. Para comparar UDP com o uso TCP, divida fluxos de áudio de TCP por fluxos de áudio de UDP para determinar uma porcentagem. Um valor de mais de 1% precisa ser investigados ainda mais.

No exemplo acima, pegamos 1,806 fluxos TCP divididos por 10,481 fluxos UDP chegar a um valor de 17.2%. Esse valor é bem acima % 1 e nos diz que precisamos continuar nossa investigação para determinar onde o uso TCP está ocorrendo.

Também é incluída no relatório é a porcentagem de áudio ruim. Isso proporciona um modo de exibição para a comparação de qualidade da chamada entre UDP e TCP para ajudar a visualizar como TCP está afetando a qualidade da chamada overcall.

Então agora que você determinou que não há um alto uso de áudio com base em TCP em sua organização, o que fazer em seguida? Vá para os relatórios de **fluxos TCP Construindo e sub-rede** para dividir o uso TCP pelo construção e sub-redes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Fluxos TCP Construindo e sub-rede

Nos modelos de CQD fornecidos, vá para os fluxos TCP por sub-rede e criação de relatórios de tabela usando o gerenciada ou modelo de todas as redes. Há três relatórios incluídos no modelo, um para investigando conferência, com e sem informações de retransmissão da Microsoft e outro para investigando chamadas de duas partes. Para fins de investigar o uso TCP, o processo é a mesma, portanto focaremos a discussão na conferência somente.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                                  |

![Relatório que lista os fluxos TCP, organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image25.png)

_Figura 25 – TCP fluxos, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o volume de uso do TCP. Um relatório adicional também está incluído para identificar o IP de retransmissão Microsoft que foi usado na chamada para ajudar a isolar ausentes regras de firewall. Concentre os esforços de remediação nesses prédios que têm o maior volume de fluxos de áudio para maximizar o impacto.

A causa mais comum de uso do TCP está faltando regras de exceção no firewalls ou proxies. Voltaremos falando proxies na próxima seção, portanto por enquanto concentrar os esforços nos firewalls. Usando o edifício ou sub-rede fornecido, você pode determinar o firewall que precisa ser atualizado.

_Tabela 10 - remediação * orientação para fluxos TCP Construindo e sub-rede_

| Remediação        | Orientação     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar o firewall | Verifique se [as portas de IP do Office 365 e endereços](https://aka.ms/o365ips) são excluídos do seu firewall. Embora haja muitos endereços IP e portas que precisam ser aberto, problemas relacionados a mídia TCP, concentrar os esforços iniciais no seguinte: Verifique se as seguintes [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) estão em suas regras de firewall. Referir-se a linha 4 na tabela mostrada para obter informações de sub-rede de mídia específicos. [As portas UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): essas portas são as portas de mídia preferencial e devem ser abertas, caso contrário, o cliente falhará volta para a porta TCP 443. |
| Verifique se             | Use a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas de conectividade para portas e endereços IP do Office 365 específicos do edifício afetado ou sub-rede.    |

### <a name="investigate-http-proxy-usage"></a>Investigue o uso do proxy HTTP

Os proxies HTTP não é o caminho preferido para estabelecer sessões de mídia, para uma infinidade de motivos. Muitas contêm recursos de inspeção de pacotes profunda que pode impedir conexões ao serviço sejam concluídas e introduzir interrupções causadas. Além disso, os proxies talvez forçar TCP em vez de permitindo UDP, que é recomendado para melhor qualidade de áudio.

É sempre a recomendação da Microsoft para configurar o cliente para conectar-se diretamente a equipes e Skype para serviços corporativos. Isso é especialmente importante para o tráfego de mídia-based.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Fluxos de áudio com o uso de proxy HTTP geral

Este relatório descreve o uso de proxy ao longo do tempo em uma escala mensal. O relatório de fluxo de proxy HTTP nesta seção do modelo é muito semelhante os relatórios TCP. Ele não parece estar em estejam de chamadas ruins ou BOM, mas se a chamada é conectada por HTTP.

![Captura de tela dos fluxos de áudio com o relatório de uso do Proxy HTTP no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image26.png)

_Figura 26 – fluxos de áudio com o uso de Proxy HTTP_

##### <a name="analysis"></a>Análise

Se você vir um alto volume de uso do HTTP, consulte sua equipe da rede para garantir que as exclusões adequadas estejam em vigor para que os clientes são roteamento diretamente para equipes ou Skype para sub-redes de mídia Business Online. Idealmente, não deve haver nenhum uso do HTTP exibido aqui.

Se você tiver apenas um proxy de internet em sua organização, verifique as adequadas [URLs do Office 365 e exclusões de intervalo de endereços IP](https://aka.ms/o365ips). Se mais de um proxy de internet está configurado em sua organização, aproveitar o HTTP sub-recursos relatado para isolar qual construção ou sub-rede é afetado.

Para organizações que não é possível ignorar o proxy, certifique-se que o Skype para o cliente de negócios está configurado para entrar em corretamente quando ela está localizada atrás de um proxy conforme descrito no artigo [Skype para negócios deve usar servidor proxy para entrar em vez de tentar direta conexão](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Fluxos de proxy HTTP Construindo e sub-rede

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o uso do HTTP.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                        |

![Captura de tela do uso do Proxy HTTP pelo relatório de criação e a sub-rede em que o painel de controle de qualidade de chamada.](media/quality-of-experience-review-guide-image27.png)

_Figura 27 – sub-rede e uso de Proxy HTTP, criando_

##### <a name="remediation"></a>Remediação

Concentre os esforços de remediação em qualquer prédios ou as sub-redes com o uso de proxy HTTP. A causa mais comum de uso do HTTP está faltando regras de exceção de proxies. Usando o edifício ou sub-rede fornecido, você pode determinar qual proxy precisa ser atualizado.

Verifique se os [FQDNs do Office 365](https://aka.ms/o365ips) de necessários são excluídos do seu proxy.

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção se concentra nas tarefas de relatórios sobre o Skype para versões do cliente de negócios – específicas e o uso de dispositivos de certificados.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="determine-client-versions"></a>Determinar as versões do cliente

O relatório neste espaço enfoca identificando Skype para versões do cliente de negócios em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio de rede conteúdo de entrega Azure (CDN) e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.

Números de versão do Skype para negócios 2015 e 2016 podem ser encontrados por meio de links a seguir:

-   [Liberações de canal de atualização de cliente Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versão e compilação do Office 365 para clique para executar](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para downloads de negócios e atualizações](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.  

> [!IMPORTANT]
> Relatórios de cliente exigem que você excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. |

![Captura de tela do relatório de cliente e dispositivos no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image28.png)

_Figura 28 - relatório da versão de cliente_

#### <a name="remediation"></a>Remediação

Uma parte importante de dirigir experiências do usuário de alta qualidade é garantir que os clientes de gerenciada estão executando versões atualizadas do Skype para negócios. Isso oferece vários benefícios, entre eles:

-   É mais fácil gerenciar algumas versões versus muitas versões.

-   Ele fornece um nível de consistência da experiência.

-   Ele facilita a solucionar problemas de qualidade de chamada e usabilidade.

-   A Microsoft dá continuamente aperfeiçoamentos gerais e as otimizações em todo o produto. Garantir que os usuários recebam essas atualizações reduz os riscos de executar um problema que já foi resolvido.

Limitar sua implantação para as versões do cliente que são menos de seis meses, melhorar a experiência geral do usuário e melhorar a capacidade de gerenciamento em comparação a ter grandes números de diferentes versões do cliente no mesmo ambiente.

Se você estiver usando somente Office Click-to-Run, você estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional será necessária.

If, como a maioria das organizações, você tem uma mistura de pacotes Click-to-Run e installer (MSI), você pode usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Concentre seus esforços nesses clientes onde o volume está acima da média. Se você observar que os clientes são atrasado, trabalhar com a equipe responsável pelo gerenciamento de atualizações do Office e garantir que eles estiver aprovando e Implantando patches de cliente regularmente.

### <a name="devices-investigations"></a>Investigações de dispositivos

Para tornar use destes relatórios dispositivo, é melhor entender o conceito de médio de opinião pontuação (MOS). MOS é a medida padrão ouro para medir a qualidade de áudio perceptivelmente. Ele é representado como uma classificação de inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade de voz. Como ela é afetada pela percepção humana, é naturalmente subjetiva. Existem várias metodologias diferentes para testar subjetiva.
A maioria das medidas de qualidade de voz são baseados em uma escala de classificação (ACR) categorização absoluta.

Em um teste subjetivo ACR, um número significativo de estatística de pessoas classificar seu qualidade da experiência em uma escala de 1 (ruim) a 5 (excelente). A média das pontuações é o MOS. O MOS resultante depende do intervalo de experiências que foram expostos ao grupo e ao tipo de experiência sendo classificada como.

Porque ele é impraticável para conduzir testes subjetivas de qualidade de voz para um sistema de comunicação em tempo real, equipes e Skype para negócios geram valores MOS usando algoritmos avançados objetivamente prever os resultados de um teste subjetiva.

O conjunto disponível de MOS e métricas associadas fornecem um modo de exibição para a qualidade da experiência de ser entregue aos usuários.

Fornecendo aos usuários com dispositivos certificados para equipes e Skype for Business, você reduz a probabilidade de encontrando experiências negativas devido ao próprio dispositivo (que é mais provável, por exemplo, com microfones e alto-falantes laptop internas). Para obter mais informações, consulte [telefones e dispositivos para Skype para negócios](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso organizacional dos dispositivos de captura (microfones) por volume

Este relatório é usado para avaliar o uso de microfone por volume e de pontuação do MOS e pode ser encontrado nos modelos acompanha em clientes e dispositivos *.*

> [!IMPORTANT]
> Relatórios de dispositivo exigem que você poderá excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. 

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.<br><br> Você poderá observar quando visualizem esse relatório que você veja o mesmo dispositivo relatado várias vezes. Isso acontece devido à maneira como o dispositivo é informado de serem reportados para CQD. Diferenças de hardware e de localidade do sistema operacional relatar dados do dispositivo de forma diferente.

![Captura de tela do relatório de dispositivos (microfone) no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – relatório de dispositivo (microfone)_

##### <a name="remediation"></a>Remediação

A primeira tarefa é determinar o alvo de MOS que você gostaria de obter. Intervalo de 1 a 5, com 5 sendo o melhor de pontuações MOS. Escolha um destino razoável, com base em seu ambiente e os resultados da consulta. No exemplo a seguir, o destino será uma pontuação do MOS de 3.6 ou superior para todos os dispositivos que tenham mais de 100 fluxos. Você obterá a qualidade do dispositivo de destino quando:

-   Os resultados da consulta de dispositivo retornam MOS \> 3.6 para NumStreams \> 100

Normalmente, você precisará substituir dispositivos com desempenho insatisfatório por dispositivos de certificados. Algumas considerações quando analisando o relatório de dispositivo incluem:

-   São dispositivos certificados ou conhecidos para ser boas em seu ambiente? Se um dispositivo de certificados ou boa é retornado na consulta com uma pontuação do MOS inferior que sua linha de base, pode haver desconhecidos fatores adicionais (por exemplo, uma rede ruim ou pc capacidade suficiente) que está contribuindo para a pontuação baixa.
    Investigação adicional será necessária.

-   Você pode identificar os usuários de um dispositivo por meio da [Análise de chamada](#call-analytics-training). Verifique para garantir que eles têm os drivers de dispositivo mais recentes e que seu dispositivo não está conectado por meio de um hub USB.

-   Verificar se há uma correlação entre dispositivos ruim e tornar um determinado do sistema e modelo. Em caso afirmativo, o dispositivo talvez não seja compatível ou precisa de atualizações de driver.

A segunda tarefa é determinar o uso geral de dispositivos não-certificados. É recomendável que pelo menos de 80 por cento de todos os fluxos de áudio de usar um dispositivo de certificados.
Isso é realizado melhor exportando o relatório de dispositivos para o Excel e manualmente Calculando o uso de dispositivos de certificados ou aprovados. As organizações geralmente manter uma lista de todos os dispositivos aprovados, para que filtragem e classificação dos dados devem ser simples.

## <a name="appendix-a-lync-networking-guide"></a>Guia de rede do apêndice Lync r.

Para obter mais informações em equipes e Skype para conceitos de rede de negócios e o raciocínio por trás de sua importância a qualidade, o [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) é aplicável.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de desempenho do apêndice B. rede

A qualidade de mídia em tempo real (áudio, vídeo e compartilhamento de aplicativos) sobre IP significativamente é afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter melhor equipes ou Skype para qualidade de mídia de negócios, sua rede deve atender aos seguintes métricas de desempenho de rede.

_A tabela 11 - requisitos de desempenho de rede_

| Métrica                           | Cliente para o Microsoft Edge           | Edge do cliente para o Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latência (uma maneira)                | \<50 ms                            | \<30 ms                            |
| Latência (tempo de resposta ou tempo de ida e volta) | \<100 ms                           | \<60 ms                            |
| Perda de pacotes de intermitência                | \<10% durante qualquer intervalo de 200 ms   | \<1% durante qualquer intervalo de 200 ms    |
| Perda de pacote                      | \<1% durante qualquer intervalo de 15 segundos    | \<0,1% durante qualquer intervalo de 15 segundos  |
| Tremulação de entre chegada de pacotes      | \<30 ms durante qualquer intervalo de 15 segundos | \<15 ms durante qualquer intervalo de 15 segundos |
| Reordenar de pacotes                   | \<% de 0,05 pacotes de fora de ordem       | \<pacotes de fora de ordem 0,01%      |

Para obter mais informações, consulte o artigo a seguir sobre o [desempenho de rede e qualidade de mídia](https://aka.ms/performancerequirements) para equipes e Skype para negócios Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apêndice C. Outros recursos

### <a name="building-data-file"></a>Criando o arquivo de dados

-   [Ativando e usar CQD no Skype para negócios Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Treinamento de CQD

-   <https://aka.ms/sof-cqd>

-   Guia de [Introdução ao CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) e workshop.

-   [Guia on-line CQD dimensões e medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Treinamento de análise de chamada

-   [Apresentando a análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar a Análise de Chamada do Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Qual é a diferença entre a Análise de Chamada e o Painel de Qualidade de Chamadas?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas no Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Suporte de análise de chamada

-   Comunidade: [Skype para o programa de visualização de negócios](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Para obter suporte, entrar em nosso portal de visualização [www.skypepreview.com](http://www.skypepreview.com), selecione **um problema de relatório**e usar a opção **Criar novo Bug** para relatar algum problema. Observe que os engenheiros de suporte estão disponíveis para oferecer suporte de segunda à sexta-feira, entre os horários de 6 horas para 9 PM EST. Solicitações fora essas horas serão priorizadas do dia seguinte.

### <a name="devices"></a>Dispositivos

-   [Skype para soluções de negócios pessoais periféricos & PCs de catálogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Relatórios de locatário

-   [Pacote de conteúdo de adoção do Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Relatórios do Skype for Business Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Relatórios de Teams da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
---
title: Qualidade da experiência Revise o guia para equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guia para analisar o desempenho de mídia em tempo real for Microsoft Teams usando o painel de controle de qualidade de chamada (CQD).
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
  - Microsoft Teams
---

# <a name="quality-of-experience-review-guide"></a>Qualidade da experiência Revise o guia

Este guia é sobre a fase de unidade de valor para o Microsoft Teams e Skype para negócios Online. Você pode [baixar uma versão do Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) deste guia.

## <a name="introduction"></a>Introdução

Para que o maior impacto sobre como melhorar a experiência do usuário, as organizações precisam tornem operacional as principais áreas que são mostradas na figura a seguir.
Áreas adicionais incluem identificando tarefas operacionais, estabelecimento de metas para métricas de qualidade, averiguar as métricas usar para medir o êxito organizacional e estreitando áreas de investigação conforme necessário.

![Principais áreas para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuário, dispositivos e clientes.](media/quality-of-experience-review-guide-image1.png)

_Figura 1 - operacionais áreas de chave abordadas neste documento_

Continuamente avaliando e correção as áreas descritas neste documento, você pode reduzir seu potencial para afetar negativamente a qualidade da experiência dos usuários. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta

-   Baixa cobertura de Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Versões do cliente inconsistentes ou desatualizadas

-   Dispositivos de áudio não otimizados ou internos

-   Sub-redes problemáticos ou dispositivos de rede

Através de planejamento adequado e design antes de implantar equipes ou Skype para Business Online, você pode reduzir a quantidade de esforço que serão necessários para manter experiências de alta qualidade.

Este guia se concentra no uso do Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área, com uma ênfase especial para maximizar a adoção e o impacto de áudio. Todos os aprimoramentos feitos à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

Para acelerar sua avaliação, dois modelos CQD curated são fornecidos: um para o gerenciamento de todas as redes e o outro fosse filtrada para gerenciados apenas as redes (internas). Embora os relatórios de modelo de todas as redes são configurados para exibir informações de rede e de construção, ele ainda pode ser usado enquanto você trabalha em direção a coleta e carregamento de informações de construção. Carregar informações em CQD do edifício habilita o serviço aperfeiçoar os relatórios adicionando informações personalizadas de construção, rede e local enquanto distinguir interna do sub-redes externos. Para obter mais informações, consulte [mapeamento de construção](#building-mapping) posteriormente neste documento.

### <a name="what-is-the-cqd"></a>Qual é o CQD?

Use o painel de qualidade de chamada (CQD) para obtém ideias sobre a qualidade das chamadas feitas por meio de equipes e Skype para serviços corporativos. CQD foi projetado para ajudar Skype para os administradores corporativos e as equipes e os engenheiros de rede otimização a rede. CQD analisa agregam informações para uma organização inteira onde padrões gerais podem se tornar aparentes, permitindo que a equipe efetue informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de chamada que lhe dão ideia da experiência do usuário, confiabilidade de chamada e qualidade geral da chamada.

> [!NOTE]
> CQD não contém informações de identificação pessoal (PII). PII é informações que podem ser usadas por conta própria ou com outras informações para identificar, entre em contato ou localizar uma única pessoa ou para identificar um indivíduo em contexto. 

### <a name="intended-audience"></a>Público-alvo

Este documento é destinado a ser usado pelo parceiro e cliente participantes com funções como arquiteto/líder de colaboração, consultor, especialista da adoção do gerenciamento de alteração, ajuda/suporte de liderança de mesa, liderança de rede, liderança de área de trabalho e administrador de TI.

Este documento também se destina a ser usado pelo champion(s) a qualidade designada.
Para obter mais informações, consulte [a função campeão de qualidade](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este guia, verifique se que você tem as [funções](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) de locatário adequadas atribuído para que você possa acessar CQD.

-   **Função Administrador Global do office 365:** Acessa todos os recursos administrativos no conjunto do Office 365 de serviços em seu plano, incluindo Skype para negócios.

-   **Skype para a função de administrador de negócios:** Configura Skype for Business para sua organização e é capaz de exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365. Essa função é necessária, mesmo se você implantar apenas equipes.

Como alternativa, você pode atribuir a função a seguir para uma conta de usuário do Office 365 deseja permitir acesso a somente os recursos de relatório.

-   **Relata leitor:** Pode exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365, qualquer relatórios do [pacote de conteúdo do Office 365 adoção](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e relatórios CQD.

Noções básicas sobre os principais conceitos do CQD ajuda a maximizar o impacto que você pode fazer em melhorar a experiência de seus usuários com equipes ou Skype para Business Online.
Recursos adicionais podem ser encontrados no [Apêndice](#other-resources).

## <a name="what-is-quality"></a>Qual é a qualidade?

Ao discutir qualidade em equipes e Skype para os negócios, é importante definir o termo para atingir um entendimento comum. A qualidade, conforme definido aqui, é uma combinação de serviço métricas e experiência do usuário.

![Métricas de serviço são compostas das versões de chamadas ruins proporção, confiabilidade, pontos de extremidade/dispositivos e cliente. Experiência do usuário final é formada pelo percepção do usuário da qualidade de serviço.](media/quality-of-experience-review-guide-image2.png)

_Figura 2: o que há de qualidade?_

### <a name="define-your-target-metrics"></a>Definir seus métricas de destino

Esta seção discute as métricas de serviço principal que usamos para avaliar como serviços apresentem integridade. Continuamente avaliando e orientando os esforços para manter essas métricas abaixo de destino, você vai ajudar a garantir a que qualidade da chamada uniforme e confiável de experiência de seus usuários. Para começar, as metas a seguintes são fornecidas.
Vamos resumem a diferença entre uma rede gerenciada e:

-   Uma rede *gerenciados* pode ser influenciada e controlada pela organização.
    Isso inclui LAN interna, WAN remoto e VPN.

-   Uma rede *não gerenciada* não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de hotel ou aeroporto.

_Tabela 1 - métricas de avaliação de integridade de destino principais_

|               | Qualidade para redes gerenciadas | Confiabilidade para redes gerenciadas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nome de métrica   | % De taxa de chamada de áudio inválida      | Configuração da chamada % de falhas            | Recebimento de chamadas % de falhas |
| Destino da amostra | \<% 3                         | \<% 1                             | \<4%                 |

É importante discutir e definir as metas da sua organização para atender aos seus objetivos de negócios. Idealmente, você deve identificar nestes destinos antes da implantação.

#### <a name="audio-pcr-"></a>% De áudio PCR 

Áudio ruim chamada proporção (PCR) representa a porcentagem geral da organização de chamadas que têm má qualidade de áudio. Essa métrica destina-se para realçar áreas onde sua organização pode se concentrar esforço para ter um impacto mais forte em direção a redução desse valor e aprimorando a experiência do usuário, o motivo pelo qual o foco principal são as redes gerenciadas ao olhar PCR. Os usuários externos são muito importantes, mas difere de investigações em uma base organizacional e de usuário.
Considerar o fornecimento de práticas recomendadas para usuários externos e examine efetuar chamadas externas independentemente do geral da empresa.

#### <a name="call-setup-failures-"></a>Configuração da chamada % de falhas 

Isso representa qualquer sessão de mídia que não pôde ser estabelecida. Devido a gravidade do impacto sobre a experiência do usuário medida aqui, o objetivo é reduzir este valor como como próximos de zero possível. Um valor alto para essa métrica é mais comuns em novas implantações com regras de firewall incompleto do que uma implantação desenvolvido, mas ainda é importante observar regularmente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

#### <a name="call-drop-failures-"></a>Recebimento de chamadas % de falhas 

Isso se aplica a uma carga de trabalho de áudio em que a sessão terminou inesperadamente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

### <a name="service-metrics"></a>Métricas de serviço

Destinos de métricas de serviço consistem em métricas específicas baseados no cliente.

#### <a name="pcr"></a>PCR

A base para determinar se uma chamada foi classificada como ruim é usando a proporção de chamadas ruins (PCR). PCR é formada pelas métricas de rede cinco descritas na tabela a seguir. Para uma chamada para ser classificadas como insatisfatória, apenas uma métrica deve exceder o limite definido. Para obter mais informações sobre o processo de classificação de chamada, consulte [esta postagem de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabela 2 - métricas de serviço de chamadas ruins_

| Métrica                                           | Descrição                                                                                                                                                                                                                                                                                                                                                                  | Experiência do usuário                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tremulação \>30 ms                                   | Esta é a média alteração em atraso entre pacotes sucessivos. Equipes e Skype para negócios podem se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante avisos os efeitos de variação.                                                                                                                         | Os pacotes que chegam em diferentes velocidades causarão voz do alto-falante som robótica.                                                                                       |
| Taxa de perda de pacote \>10% ou 0,1                    | Geralmente, isso é definido como uma porcentagem dos pacotes que são perdidos. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos que têm quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.                                                                                                                               | Os pacotes sendo capitular e não chegada a seu destino pretendido causarão lacunas na mídia, resultando em palavras e sílabas perdidas e entrecortada vídeos e compartilhamento. |
| Tempo de ida e volta \>500 ms                         | Este é o tempo que leva para obter um pacote IP do ponto A ponto b e voltar para a ponto. Esse atraso de propagação de rede é associado à distância física entre os dois pontos e a velocidade da luz e inclui uma sobrecarga adicional tomada por vários dispositivos no caminho de rede.                                                                                  | Os pacotes demorando muito para chegar ao seu destino causam um efeito de walkie-talkie.                                                                                 |
| Média de degradação NMOS \> 1.0                  | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, juntos causado a rede [Pontuação média de opinião](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) para soltar por mais de um ponto. Isso não necessariamente significa que a conexão de rede estiver baixa, mas suficiente problemas ocorreram durante a chamada que qualidade foi reduzida. | Isso é uma combinação de tremulação, perda de pacotes, e — a um grau menor — aumento do tempo de ida e volta. O usuário pode estar apresentando uma combinação desses sintomas.          |
| Taxa média de amostras escondidas \> 7% ou 0,07 | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, causou o cliente auto-restauração a mídia. Uma amostra de áudio escondida é uma técnica costumava suave check-out a transição repentina que geralmente seria causada por pacotes de rede capitular.                                                                                                                | Valores altos indicam que significativo níveis de ocultação perda foram aplicados e resultou em áudio distorcido ou perdido.                                                  |

#### <a name="client-and-device-readiness"></a>Preparação de clientes e dispositivos

Você precisa de uma estratégia sólida de clientes e dispositivos para garantir que os usuários tenham uma experiência de usuário consistente e positivo. Cada estratégia de preparação de unidade de alguns princípios-chave.

##### <a name="client-readiness"></a>Preparação do cliente

Uma estratégia de preparação de cliente forte garante que os usuários estão executando a versão mais recente do cliente ao mesmo tempo aproveitando a melhor experiência possível.
Microsoft rotineiramente patches do Skype para clientes corporativos; garantir que você o mantenha atualizado em seu ambiente é vital para o sucesso geral.

Recomendamos que você não permita que as versões de cliente se encaixam por mais de seis meses. Se você estiver usando o Office Click-to-Run, você estiver já sendo mantidos atualizados pelo serviço. Use o [Relatório de cliente](#determine-client-versions)incluídos, conforme descrito mais adiante neste guia, para ajudá-lo com esse processo. Você também pode aproveitar os relatórios de exemplo de taxa Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de cliente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


##### <a name="device-readiness"></a>Preparação de dispositivo

Sem uma estratégia de única pode afetar a experiência do usuário mais de sua estratégia de preparação de dispositivo. A maioria das organizações são feliz remover dispositivos desnecessários de usuários (por exemplo, telefones de mesa ou outros dispositivos de áudio dedicados), e isso é geralmente uma justificativa comercial de núcleo para alternar para equipes ou Skype para negócios. No entanto, dessas organizações mesmas às vezes hesite para fornecer dispositivos de substituição, mesmo se esses dispositivos são baratos. Moderna laptops e PCs, porém equipados com interna microfone e alto-falante, não são otimizadas para empresarial voz sobre IP (VoIP). Isso geralmente cria uma experiência ruim para todos os participantes, especialmente se o alto-falante está em um ambiente com ruído. Programa de certificação da Microsoft dispositivo garante que, quando um usuário participa de uma chamada telefônica usando qualquer dispositivo certificado para equipes ou Skype for Business, ele produzirá uma experiência que é superior a usar um dispositivo não certificados.

Sempre, recomendamos que equipes e Skype para usuários comerciais usam um fone de ouvido certified ou alto-falante ao participar de uma chamada de voz usando um cliente de desktop.
Para obter mais informações sobre dispositivos de certificados da Microsoft, revise neste [artigo sobre como telefones e dispositivos qualificados](https://technet.microsoft.com/office/dn788944.aspx). Use o [Device Report](#devices-investigations), posteriormente neste guia, para obter ajuda com o gerenciamento de seus dispositivos. Também, você pode usar os relatórios de exemplo de taxa de Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de dispositivo.

### <a name="user-experience"></a>Experiência do usuário

Analisando a experiência do usuário é mais arte do que ciência, porque as métricas coletadas aqui sempre não significa que há um problema com a rede ou serviço, mas em vez disso, eles indicam que o usuário percebe um problema. A Microsoft oferece um mecanismo de pesquisa interno — conhecido como taxa meu chamada (RMC) — para ajudar a estimar a experiência geral do usuário. RMC ajudarão você a responder às seguintes perguntas da perspectiva dos usuários:

-   Saber como usar a solução?

-   É a solução fáceis de usar e intuitiva e oferece suporte a minhas necessidades de comunicação diárias?

-   A solução Ajude-me trabalho?

-   Qual é a minha percepção geral da solução?

-   Posso usar a solução em qualquer ponto no tempo, independentemente de onde estou?

-   É possível configurar e manter uma chamada?

#### <a name="rmc"></a>RMC

RMC compilado no equipes e Skype para negócios e é automaticamente configurado para ser exibida depois que um em cada 10 chamadas ou 10% de todas as chamadas. Este breve pesquisa pede ao usuário classificar a chamada e fornecer um contexto de pouca para por que a qualidade da chamada pode ter sido ruim. Uma classificação de um ou dois é considerada ruim, três ou quatro é bom e cinco é excelente. Embora seja um pouco de um indicador à demora, essa é uma métrica útil para descobrir problemas que métricas de serviço podem perder.

> [!NOTE]
> Até que os usuários são instruídos para responder às pesquisas RMC, oferecendo uma boa indicação além das respostas mal, normalmente volte como predominantemente negativo. A maioria dos usuários responder somente quando a qualidade da chamada é ruim. Dessa forma, seus relatórios RMC podem ser enviesados até o lado ruim mesmo enquanto métricas de serviço estão funcionando bem. 


Você pode usar CQD para reportar sobre as respostas do usuário RMC e relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são abordados em detalhes neste guia. Para obter mais informações sobre o RMC Skype para Business Online e orientações para instruir os usuários a fornecer respostas RMC úteis, consulte esta [postagem de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorias de qualidade

O sucesso do operacionalização de uma implantação de alta qualidade e confiável depende da sua rigor operacionais de construção. Especificamente, prestar bastante atenção em três categorias ilustrado na figura a seguir; Estes são o foco deste guia:

-   **Rede:** Qualidade de áudio com foco na métrica PCR, o uso TCP, sub-redes com e sem fio e identificando o uso de proxies HTTP e VPN.

-   **Pontos de extremidade:** Dispositivos de áudio e a versão do cliente (Skype para negócios apenas).

-   **Gerenciamento de serviços:** Essa categoria consiste em duas seções:

    -   A primeira é responsabilidade da Microsoft para gerenciar e manter as equipes e Skype para serviços corporativos Online.

    -   Segundo são tarefas de que sua organização deve gerenciar para garantir acesso confiável ao serviço, atualizando informações de criação e manutenção de firewalls para novos endereços IP do Office 365 infrastructure for adicionada ao serviço.

![As categorias de qualilty em uma organização: serviço de gerenciamento, pontos de extremidade e a rede.](media/quality-of-experience-review-guide-image3.png)

_Figura 3 - críticas categorias para equipes e Skype para implantação Business Online_

O gráfico a seguir descreve as tarefas que você deve executar para cada categoria. Recomendamos que você execute essas tarefas uma vez por semana, no mínimo.

Na primeira vez que você executar essas tarefas levarão pouco mais do que as iterações subsequentes, pois muitas dessas categorias exigem que você valide suas configurações de implantação. Depois que você tiver obtido o estado desejado atendendo os destinos que você definiu, execução dessas tarefas ajudará você manter esse estado.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Em um mundo primeiro nuvem, você deve executar algumas tarefas de gerenciamento de serviço para manter as experiências do usuário de alta qualidade. Essas tarefas variam de garantir que não há largura de banda suficiente para alcançar o serviço sem links de internet, validando que qualidade de serviço (QoS) de saturação é no lugar em todas as áreas de rede gerenciada, e — finalmente — permanecendo na parte superior [intervalos de IP do Office 365 em firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: qualidade e confiabilidade. Confiabilidade enfoca medindo a capacidade do usuário para fazer chamadas com êxito e permanecem conectadas. Qualidade enfoca a telemetria agregada enviada para equipes e Skype para Business Online pelo cliente do usuário durante e depois que ela for encerrada.

Dado o impacto crítico que confiabilidade tem sobre a experiência do usuário, começar avaliar e investigando dessas métricas antes de começar em qualidade.

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nesta categoria está validando a quais versões do cliente estiver executando o Skype para negócios em compilações da área de trabalho do últimos seis meses para garantir que os usuários estão obtendo o benefício das otimizações contínuas feitas do Skype para o cliente de desktop de negócios. Além disso, isso simplifica as tarefas de gerenciamento de cliente geral e fornece uma experiência de usuário consistente.

A área de importante é quais dispositivos estão predominantes em sua implantação de monitoramento e orientando o uso de dispositivos de certificados para oferecer a melhor experiência de usuário.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


## <a name="using-the-reports"></a>Usando os relatórios

Esta seção descreve os conceitos básicos sobre como trabalhar com CQD. Orientação é fornecida para os seguintes tópicos:

-   Localizando sua ID de Inquilino

-   Relatórios em equipes versus Skype para negócios

-   Primeiro versus segunda classificações

-   Medidas, dimensões e filtros

-   Fluxos de versus chamadas

-   Chamadas boas, ruins e não classificadas

-   Introdução ao CQD

-   Edição de relatórios no CQD

-   Filtragem de relatórios no CQD

Para obter mais aprofundado treinamento e recursos, consulte o [Apêndice](#other-resources).

### <a name="tenant-id"></a>ID do inquilino

Alguns relatórios CQD exigem a inclusão de um filtro para sua ID de Inquilino. Devido a maneira como CQD agrega os dados de telemetria participantes federada é incluída.
Embora isso sejam valioso ao analisar as métricas de chamadas ruins, os relatórios de clientes e dispositivos exigem a filtragem de dados para um locatário específico a serem excluídas telemetria participantes federada. Se você não souber seu ID do inquilino, você pode usar um dos métodos a seguir para localizá-lo.

Requisitos de permissão

-   Função de administrador global

-   Skype para a função de administrador de negócios

#### <a name="azure-ad-portal"></a>Portal do Azure AD

1.  Logon no portal do Microsoft Azure:<https://portal.azure.com>

2.  Selecione o **Azure Active Directory**.

3.  Em **Gerenciar**, selecione **Propriedades**. A ID do inquilino é mostrada na caixa **ID do diretório** .

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Instale o módulo de gerenciamento de serviço do Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra uma janela de comando do Azure PowerShell e execute o seguinte script, inserir suas credenciais do Office 365, quando solicitado:  
    **AzureRmAccount de login**

3.  A ID do inquilino está listada na saída.

#### <a name="skype-for-business-online-admin-center"></a>Skype para negócios Online Admin Center

1.  Ir para<https://portal.office.com>

2.  Entrar com sua conta organizacional do administrador de locatário.

3.  Selecione **Skype para negócios** sob **Centros do administrador**.

4.  A ID do inquilino está listada como **ID da organização** , na página de boas-vindas.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para negócios Online usando o PowerShell

1.  [Conectar-se ao Skype para negócios Online por meio do PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Execute o seguinte comando:  
    **.Tenantid (get-cstenant)**

3.  A ID do inquilino é exibida como um GUID.

### <a name="teams-vs-skype-for-business"></a>As equipes versus Skype para negócios

CQD pode relatar equipes e Skype para telemetria de negócios. No entanto, pode haver ocasiões em que você deseja desenvolver um relatório a ser analisado telemetria de equipes separada do Skype para negócios.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios de resumo a ser analisado apenas equipes ou Skype para negócios, selecione o menu suspenso de **Filtro de produto** da parte superior da tela e selecione o produto desejado.

![Captura de tela do painel de qualidade de chamada refletindo um menu drop-down mostrando a opção de filtragem por carga de trabalho.](media/quality-of-experience-review-guide-image4.png)

_Figura 4 - Selecione um filtro de produto_

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar um relatório detalhado, adicione o filtro **É equipes** ao relatório e defini-la como True ou False. Para obter mais informações, consulte [relatórios de edição](#editing-reports) , mais adiante nesta seção.

![Captura de tela do painel de qualidade de chamada que descrevam o servidor de dados que pode ser adicionado a um relatório detalhado.](media/quality-of-experience-review-guide-image5.png)

_Figura 5 - adicionando um filtro de Teams da Microsoft a um relatório_

### <a name="dimensions-measures-and-filters"></a>Medidas, dimensões e filtros

Uma consulta CQD bem formada contém todas as três dos parâmetros a seguir:

-   **Dimensão:** Como eu desejo os dados de tabela dinâmica.

-   **Medida:** O que eu quero a ser relatado no.

-   **Filtro:** Como deseja reduzir a consulta retornar o conjunto de dados.

Outra maneira de analisar isso é uma dimensão é a função de agrupamento, uma medida é os dados que estou interessado em e um filtro é como eu quiser restringir os resultados para aqueles que são relevantes à minha consulta.

Um exemplo de uma consulta bem formado é "Mostrar-me fluxos ruins [medida] pela sub-rede [Dimension] para construção 6 [filtro]."

Para obter mais informações, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

Para filtros para os relatórios usados nos modelos de CQD, medidas e dimensões, consulte o [Apêndice](#CQD-training).

### <a name="first-vs-second"></a>Primeiro versus segundo 

Muitas das dimensões e medidas em CQD são classificadas como primeira ou segunda.
CQD não usa os campos de chamador/receptor — eles tiverem sido renomeado _primeiro_ e _segundo_ porque há etapas intermediárias entre o chamador e o receptor. A seguinte lógica determina qual ponto de extremidade envolvido no fluxo ou na chamada é rotulado como o primeiro:

-   Primeiro sempre será um ponto de extremidade do servidor (servidor de conferência, o servidor de mediação e assim por diante) se um servidor que está envolvido na chamada ou stream.

-   Em segundo lugar sempre será um ponto de extremidade do cliente, a menos que o stream está entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade são do mesmo tipo, a escolha do qual é a primeira é baseada em ordem interna da categoria de agente de usuário. Isso assegura que a ordenação seja consistente.

Para obter mais informações sobre como determinar o ponto de extremidade de primeiro ou segundo quando eles estão ambos os mesmos, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream versus chamada

Você precisa entender a diferença entre uma chamada e um stream adequadamente escolher quais dimensões ou medidas você vai ser observando em CQD.

**Stream:** Um fluxo existirá apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são exigidos para a comunicação. Fluxos são úteis para analisar os prédios ou redes. Em alguns casos, a chamada e stream são usados no nome de usuário (por exemplo, fluxo de instalação chamada ou chamada ignorados Stream).
Eles ainda são classificados como único fluxos.

**Chamar:** Uma chamada é um agrupamento de todos os fluxos de todos os participantes. Consiste em uma chamada — no mínimo — dois fluxos. Uma única chamada terá dois participantes cada com um mínimo de um stream. As chamadas são úteis para análise de tendências ao longo do tempo.

Para obter orientação adicional sobre a dimensão ou medida fizer referência a uma chamada ou um stream, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada por como BOM, baixa ou não classificados. Vamos falar sobre cada uma em mais detalhes um pouco.

**BOM ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado.
Determinar se uma chamada é bom ou ruim está descrito [neste guia](#pcr).

**Não classificados:** Uma chamada não classificada não contém um conjunto completo de métricas de serviço. Essas são frequentemente chamadas curtas — geralmente menor que 60 segundos — onde não puderam ser computadas médias e um relatório de QoE não foi gerado.

### <a name="access-cqd-online"></a>Acesso CQD Online

Você pode acessar CQD de duas maneiras.

-   Vá para <https://cqd.lync.com>.

-   Vá para **Skype para centro de administração de negócios** \> **Ferramentas**e selecione o link para CQD, conforme mostrado abaixo.

![Captura de tela mostrando "ferramentas" selecionadas no painel de navegação esquerdo e o link para "Skype para Business Online chamada qualidade Dashboard" selecionada.](media/quality-of-experience-review-guide-image6.png)

_Figura 6 – acessando CQD por meio do Skype para centro de administração de negócios_

### <a name="getting-started"></a>Introdução

Quando você procurar primeiro CQD, você verá a página relatórios de resumo. A maioria dos relatórios descritos neste guia são relatórios detalhados personalizados. Para começar a usar os relatórios detalhados, selecione **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

![Captura de tela de depcting o painel de controle de qualidade de chamada os diferentes tipos de relatórios que estão disponíveis.](media/quality-of-experience-review-guide-image7.png)

_Figura 7 - navegando para relatórios detalhados_

A página de relatórios detalhados no CQD se parece com a figura mostrada abaixo.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório.](media/quality-of-experience-review-guide-image8.png)

_Figura 8 - página de relatórios detalhados_

1.  O painel Resumo mostra contexto para o conjunto de relatório que aparece à direita.

2.  Você pode selecionar **Editar** no painel Resumo para definir propriedades de nível de relatório – (incluindo a altura do eixo y).

3.  Navegação estrutural ajuda os usuários a identificar sua localização atual na hierarquia do conjunto de relatório.

4.  Relatórios que têm filhos relatórios são mostrados com um link azul. Selecionando o link, você pode analisar os relatórios de filho.

Aponte para os gráficos de barras e as linhas de tendência para exibir valores detalhados. O relatório que tem o foco mostrará no menu Ação: **Editar**, **Clone**, **Excluir**, **Baixar**e **Exportar árvore de relatório**.

### <a name="editing-reports"></a>Edição de relatórios

Quando você seleciona **Editar** no menu Ação, de um relatório, você vai abrir o Editor de consulta. Cada relatório é feito por uma consulta. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de consulta é uma interface do usuário para edição essas consultas além das opções de exibição para o relatório, como ilustrado na figura a seguir.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório quando o relatório está sendo editado.](media/quality-of-experience-review-guide-image9.png)

_Figura 9 - Editor de relatório_

1.  Você escolher medidas, dimensões e filtros de painel à esquerda. Apontando para um valor existente exibe um botão Fechar (**X**) que você pode optar por remover o valor.

    1.  Selecionando a dimensão ou medida, você pode alterar o título editando o campo **cargo** . Você também pode alterar a ordem selecionando o azul aumentar ou diminuir setas no painel superior.

    2.  Selecionando (**+**) ao lado de um título abre a caixa de diálogo para adicionar uma nova dimensão, uma medida ou um filtro.

    3.  Digite as primeiras letras da dimensão, medida ou filtro no **encontrar um** campo para filtrar a lista para facilitar a pesquisa.

2.  O painel superior mostra as opções de personalização do gráfico.

3.  O Editor de consulta mostra uma visualização do relatório.

4.  Use a caixa **Editar** na parte inferior da tela para criar ou editar uma descrição detalhada do relatório.

### <a name="filtering-reports"></a>Filtragem de relatórios

Os modelos fornecidos inclui várias consultas integradas e filtros do relatório. As seções a seguir descrevem os filtros mais comuns usados em todo os modelos.

#### <a name="cqd-filter"></a>Filtro CQD

Você pode usar o filtro CQD ou o filtro de URL, filtrar temporariamente cada consulta de relatório. O filtro de CQD mais comuns que você utilizará é filtrar relatórios a serem excluídas telemetria participantes federada. Recomendamos que você crie um indicador esse filtro para que ele se torna o modo de exibição padrão. Excluindo dados federados de relatórios CQD é útil quando você estiver correção prédios gerenciados ou redes onde os dados federados podem influenciar seu relatório.

Para implementar um filtro CQD, na barra de endereço do navegador, acrescente o seguinte ao final da URL:

/Filter/ [AllStreams]. [Id do inquilino segundo] \|[Sua ID do INQUILINO aqui]

**Exemplo:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Id do inquilino segundo] \|[TENANTID] & locatário = TENANTID

> [!NOTE]
> O exemplo de URL acima destina-se somente a representação visual. Use o link CQD padrão de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta são implementados usando o Editor de relatório. Esses filtros são usados para reduzir o número de registros retornados por CQD, minimizando o tamanho de geral do relatório. Isso é especialmente útil para filtragem de redes não gerenciados.
Os filtros abaixo usam expressões regulares (RegEx).

_Tabela 3 - filtros de consulta_

| Filtro               | Descrição          | Exemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores em branco         | Alguns filtros não tem a opção para filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e definir o filtro é igual a ou não for igual a, dependendo das suas necessidades.                                                                                                                             | Construção do segundo nome \< \> \^ \\s\*\$                       |
| Populares sub-redes residencial | Sem um arquivo de construção válido para separar gerenciada de redes não gerenciados, redes domésticas terão obter incluídos nos relatórios. Essas sub-redes residencial estão fora do escopo do controle de TI e podem ser rapidamente excluídos de um relatório. Populares sub-redes residencial, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Inside versus fora   | Usado para filtrar um relatório para (interna) gerenciado ou (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.                                                                                                                                                                                | Segundo dentro Corp = dentro                               |

#### <a name="report-filters"></a>Filtros do relatório

Filtros do relatório são implementados adicionando um filtro ao relatório renderizado tanto no relatório Editor ou diretamente ao relatório. Os filtros de relatórios a seguir são usados em todo o modelo.

_Tabela 4 - filtro de relatório_

| Filtro     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Comece com o ano primeiro e, em seguida, mês. | 10 de 2017                           |
| Alfabético | Filtra quaisquer caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos os caracteres numéricos.    | [0-9]                             |
| Porcentagem | Filtra uma porcentagem.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar os modelos CQD

Este guia inclui [dois modelos CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Esses modelos aceleram seu uso de CQD e fornecem a você uma oportunidade para aproveitar rapidamente os recursos do CQD para tornar um impacto sobre equipes ou do Skype dos usuários para a experiência de negócios. O modelo de todas as redes, porém otimizado para funcionar com um edifício pode ser usado o arquivo de dados, enquanto você trabalha em direção a coleta e carregamento de informações de construção em CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) em CQD Online**

1.  Vá para <https://cqd.lync.com>.

2.  Autentica usando suas credenciais administrativas do Office 365.

> [!NOTE]
> Você deve ter o Office 365 Global administrador Skype para administrador de negócios ou função de leitores de relatório acessar CQD. 


3.  Selecione o menu de **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

4.  No painel Resumo, selecione **Importar**. Vá para o CQDX salvo local, selecione o modelo CQDX e selecione **Abrir**.

5.  Depois que o modelo for carregado, uma janela pop-up será exibida a mensagem "a importação de relatório teve êxito." Selecione **Okey.**

![Captura de tela de uma janela pop-up que notifica o usuário se o modelo foi importado com êxito.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita as etapas 4 e 5 para o segundo modelo CQD.

> [!NOTE]
> Os modelos CQD são importados por usuário. Se outros usuários precisarem usar o relatório, eles devem entrar e importar os modelos em sua instância CQD. 


## <a name="building-mapping"></a>Mapeamento de construção

Em um equipes ou Skype para implantação Business Online, todos os clientes são externos.
Que tem a implicação que, por padrão, todos os clientes são indicados como fora em CQD Online, independentemente de se o cliente foi conectado em uma rede corporativa interna.

Quando você trabalha com a qualidade de chamada, você precisa saber o local de um cliente e se ele foi conectado a uma rede que você pode gerenciar ou de uma rede não é possível gerenciar — a pressuposição sendo que você só pode melhorar redes você pode gerenciar.
Carregando informações de construção e rede para CQD Online, você deve habilitar CQD determinar se um cliente foi conectado a uma rede interna de corporativo/gerenciados ou a uma rede externa/não gerenciados.

### <a name="building-data-file-structure"></a>Estrutura do arquivo de dados de construção

O formato do arquivo de dados que você carrega deve atender aos seguintes requisitos para passar a verificação de validação antes de carregar.

-   O arquivo deve ser um arquivo TSV, o que significa que, para cada linha, cada coluna é separada por um caractere de tabulação, ou um arquivo CSV no qual cada coluna é separada por uma vírgula.

-   O arquivo não pode ser maior do que 50 MB.

-   O conteúdo dos dados de arquivo *não deve incluir cabeçalhos de tabela*. Em outras palavras, a primeira linha do arquivo de dados deve ser dados reais, e não os títulos de coluna, como "Rede".

-   Para cada coluna, o tipo de dados só pode ser cadeia de caracteres, número ou Bool. Se o tipo de dados for um número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.

-   Para cada coluna, se o tipo de dados é a cadeia de caracteres, os dados podem estar vazios (mas ainda devem ser separados por um delimitador apropriado, que é um caractere de tabulação ou por vírgula). Isso simplesmente atribui esse campo um valor de cadeia de caracteres vazia.

-   Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados descrito na tabela a seguir, e as colunas devem estar na ordem listada na tabela.

_Tabela 5 - Criando a estrutura do arquivo_

| Nome da coluna        | Tipo de dados | Exemplo                   | Orientação    |
|--------------------|-----------|---------------------------|-------------|
| Rede            | Cadeia de caracteres    | 192.168.1.0               | Obrigatório    |
| NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-mar-1 | Necessário\*  |
| NetworkRange       | Número    | 26                        | Obrigatório    |
| BuildingName       | Cadeia de caracteres    | SEATTLE-MAR-1             | Necessário\*  |
| OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional    |
| BuildingType       | Cadeia de caracteres    | Terminação de IT            | Opcional    |
| BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional    |
| Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado |
| CEP            | Cadeia de caracteres    | 98001                     | Recomendado |
| País            | Cadeia de caracteres    | CONOSCO                        | Recomendado |
| Estado              | Cadeia de caracteres    | WA                        | Recomendado |
| Região             | Cadeia de caracteres    | MSUS                      | Recomendado |
| InsideCorp         | Bool      | 1                         | Obrigatório    |
| ExpressRoute       | Bool      | 0                         | Obrigatório    |

\*Embora não seja necessário por CQD, os modelos estão configurados para exibir a criação e a rede nome.

#### <a name="supernetting"></a>Combinação de redes

Você pode usar a combinação de redes, geralmente chamado de roteamento entre domínios sem classificação (CIDR), no lugar de definição de cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR. Combinação de redes é suportada, mas não recomendamos utilizá-lo.

Por exemplo, a construção de marketing da Contoso é composta das sub-redes abaixo:

-   10.1.0.0/24 – primeiro andar

-   10.1.1.0/24 – 2º andar

-   10.1.2.0/24 – 3º andar

-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR — neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0

-   Intervalo de rede = 22

Aqui estão algumas coisas a considerar antes de implementar a combinação de redes:

-   Combinação de redes demora menos tempo desde o início, mas que se refere ao custo reduzir o aperfeiçoamento em termos de seus dados. Digamos que não há uma sub-rede de envolvendo do problema de qualidade 200.1.2.0. Se você implementou a combinação de redes, você não saberá onde a sub-rede está localizada no edifício ou tipo de rede que está (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes de um edifício e carregado informações de local andar, você poderá ver essa distinção.

-   É importante garantir que o endereço de supernetted/CIDR está correto e se não está capturando sub-redes indesejadas.

-   Combinação de redes pode ser usada em um mapeamento de construção com máscara de 8 bits para 28 bits.

-   Ele é bastante comum para encontrar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outras pessoas, esse é o esquema de endereço IP de um escritório de satélite. Se sua organização tem escritórios que usam essa configuração, não incluí-lo em seu arquivo de construção conforme é difícil distinguir entre redes domésticas e internos usando sub-redes comuns.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todas as novas criar carregamentos de arquivos de dados será verificado para todos os intervalos de sobreposição. Se você carregou anteriormente um arquivo de construção, você deve baixar o arquivo atual e carregá-la novamente para identificar qualquer sobreposições e corrigir o problema. Qualquer sobreposição nos arquivos carregados anteriormente pode resultar em mapeamentos de sub-redes aos prédios nos relatórios errados. 


#### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Office 365 — que é onde os dados CQD originados de — inclui um sinalizador VPN. No entanto, esse sinalizador depende de relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN registrado é um adaptador de acesso remoto. Nem todos os fornecedores VPN adequadamente registre os adaptadores de acesso remoto. Dessa forma, você não poderá usar os filtros de consulta VPN internos. Há duas abordagens para acomodar sub-redes VPN no edifício arquivo de informações.

-   Defina um **Nome de rede** usando o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma sub-rede VPN](media/quality-of-experience-review-guide-image10.png)

_Figura 10 - VPN usando o nome de rede_

-   Defina um **Nome de construção** usando-se o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma definição de construção que consiste em uma sub-rede VPN.](media/quality-of-experience-review-guide-image11.png)

_Figura 11 - VPN usando o nome do edifício_

> [!IMPORTANT]
> Determinadas implementações de VPN com precisão não relatam informações de sub-rede. Se isso ocorrer em seu relatório, que é recomendável que, quando você adiciona uma sub-rede VPN para o arquivo de construção, em vez de uma entrada para a sub-rede, adicione entradas separadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você tem 253 linhas, com uma linha para cada endereço de 172.16.18.1/32 por meio de 172.16.18.254/32, inclusive.


> [!NOTE]
> Conexões VPN são conhecidas por cometem erros conforme com fio quando a conexão de internet subjacente está na identificação de conexão de rede sem fio. Ao olhar qualidade em conexões VPN, você não pode assumir que o tipo de conexão foi identificado com precisão.

### <a name="uploading-building-information"></a>Carregar informações de construção

O painel de relatórios de resumo de CQD inclui uma página de **Carregamento de dados de Inquilino** , acessada selecionando a marca de link de **Carregamento de dados de Inquilino** no canto superior direito (procure o ícone de engrenagem). Esta página é usada para os administradores para carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeando cada ponto de acesso sem fio e seu endereço MAC e assim por diante.

1.  Vá para CQD Online navegando até <https://cqd.lync.com>.

2.  Selecione o ícone de engrenagem no canto superior direito e escolha o **Carregamento de dados de Inquilino** na página **Relatórios de resumo** .

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que é exibido enquanto dados está sendo carregados.](media/quality-of-experience-review-guide-image12.png)

_Figura 12 - menu de carregamento de dados de Inquilino_

1.  Como alternativa, se essa for a primeira vez em que visitando CQD, você será solicitado para carregar dados de construção. Você pode selecionar **Carregar Agora** para navegar rapidamente para a página de **Carregamento de dados de Inquilino** .

![Captura de tela de um banner no painel de qualidade de chamada que notifica o usuário para carregar dados de construção.](media/quality-of-experience-review-guide-image13.png)

_Figura 13 - Criando banner de carregamento de dados_

1.  Na página de **Carregamento de dados de Inquilino** , selecione **Procurar** para escolher um arquivo de dados.

2.  Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, especifique uma data de término.

3.  Depois de selecionar a **Data de início**, selecione **carregar** para carregar o arquivo para o CQD. <br><br>Antes do arquivo for carregado, ele será validado. Se a validação falhar, uma mensagem de erro é exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que descreve uma mensagem de erro ao importar dados de construção.](media/quality-of-experience-review-guide-image14.png)

_Figura 14: Criando o erro de carregamento de dados_

4.  Se nenhum erro ocorrer durante a validação, o carregamento de arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregados na **Minhas carregamentos de** tabela, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já tiver carregado um arquivo de construção e precisa para adicionar as sub-redes que podem ter sido perdidas ou excluídos, modifique o arquivo original adicionando novas sub-redes, remova o arquivo atual e reenvie o arquivo recentemente editado. Pode haver construção ativa apenas um arquivo de dados em CQD. 

### <a name="missing-subnets"></a>Sub-redes ausentes

Após carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre é o caso; Normalmente, as sub-redes alguns são perdidas. Esta seção aborda como validar as redes ausentes.

Navegue até a página de **Relatórios detalhados** no CQD Online e navegue até o **Relatório de sub-rede ausentes** incluídas nos modelos CQD. Isso apresenta todas as sub-redes com 10 ou mais áudio fluxos que não são definidos no edifício arquivo de dados. Certifique-se de que não há nenhuma redes gerenciadas nessa lista. Se não existirem sub-redes, atualize o edifício original do arquivo de dados e reenvie a CQD.

> [!IMPORTANT]
> Você precisará adicionar sua ID de Inquilino como um filtro de consulta para a **Segunda ID do inquilino** para este relatório para filtrar o relatório para exibir somente os dados de inquilinos da sua organização. Caso contrário, o relatório mostrará sub-redes federados.

> [!NOTE] 
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.                                                  |

![Relatório mostrando as sub-redes não são incluídos no arquivo de dados de construção CQD que mostram o uso.](media/quality-of-experience-review-guide-image15.png)

_Figura 15 - ausente relatório de construção_

## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para aprimorar a qualidade é para avaliar o estado de confiabilidade de áudio em toda a organização. Confiabilidade de áudio, pois é vital para uma experiência de usuário positivo iniciamos com os dois componentes que medem confiabilidade:

1.  **Falhas de instalação de chamada:** Sessão não pôde ser estabelecida.

2.  **Falhas de recebimento de chamadas:** Sessão foi estabelecida e finalizada inesperadamente

Ao longo desta seção, abordaremos métodos para ambas as áreas de investigar.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações.


### <a name="call-setup"></a>Configuração da chamada

Priorize remediando falhas de instalação chamada nessa área em primeiro lugar, pois essas falhas possuem um impacto negativo significativo na experiência do usuário.

Começar a investigação avaliando a porcentagem de falhas de instalação chamada geral para a organização e, em seguida, priorizar áreas de investigação com base na porcentagem mais alta, criação ou da rede.

#### <a name="call-setup-failures-overall"></a>Falhas de instalação gerais de chamadas

Este relatório de gráfico exibe a quantidade total de chamada bem sucedida, configurar e falhas de instalação de chamadas ao longo do tempo. Aponte para qualquer uma das colunas para exibir seus valores individuais, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico que mostra o percentual de falha na instalação do fluxo de chamadas de áudio](media/quality-of-experience-review-guide-image16.png)

_Figura 16 - confiabilidade de áudio - falhas de instalação de fluxo de chamada_

##### <a name="analysis"></a>Análise

Este relatório exibe o uso da instalação chamada de áudio e falhas de sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas e determinar sua próxima ação:

1.  Qual é a porcentagem de falha de instalação chamada total para o mês atual?

2.  É a porcentagem de falha de instalação chamada total abaixo ou acima a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório informará a história da frequência suas configurações gerais de chamada estão falhando em toda a organização.

Independentemente das respostas anteriores, reserve um tempo para investigar maior usando os sub-relatórios incluídos para procurar por qualquer prédios individuais ou redes que possam precisar de remediação. Embora a taxa de falha geral pode estar abaixo na métrica de destino, geralmente as taxas de falha para uma ou mais redes ou prédios são acima na métrica e precisam remediação.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Falhas de instalação de chamada Construindo e sub-rede 

Este relatório de tabela é usado para descobrir e isolar qualquer prédios ou redes que precisam de correção.

> [!NOTE]
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.


![Relate que razões de falha de instalação de chamada de listas, organizados construindo, a rede e a sub-rede por mês.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - falhas de configuração de áudio, criando ou sub-rede_

##### <a name="remediation"></a>Remediação 

Concentre os esforços de remediação em prédios ou sub-redes que tenham o maior volume de falhas em primeiro lugar, porque isso maximizar o impacto sobre a experiência do usuário e ajudam a reduzir rapidamente as falhas de instalação chamada organizacionais.
A tabela a seguir lista as duas razões para falhas de instalação chamada conforme relatado pelo CQD.

_Tabela 6 – razões para falhas de instalação chamada_

| Chamar o motivo de falhas de instalação                       | Causa comum                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Regra de isenção de inspeção de pacotes de profundidade de firmware de ausentes | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida devido às regras de inspeção de pacotes de profundidade. Isso é provável devido às regras de firewall não está sendo configuradas corretamente. Neste caso o handshake TCP foi bem-sucedida, mas o handshake SSL não especificou.               |
| Regra de exceção do bloco de IP de firmware de ausentes               | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida com a rede do Office 365. Isso pode ser devido às regras de firewall ou proxy não está sendo configuradas corretamente para permitir acesso aos endereços IP e portas usadas para equipes e Skype para tráfego de negócios. |

Agora como começar sua remediação, é possível focar seus esforços em um edifício ou sub-rede. Conforme mostra a tabela anterior, esses problemas são devido às configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de remediação.

_Tabela 7 - próximas etapas para a chamada de correção de falha de instalação_

| Remediação           | Orientação     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewalls | Trabalhar com a equipe de rede e verifique se a sua configuração de firewalls contra [a lista de endereços IP do Office 365](https://aka.ms/o365ips). Verifique se as portas e [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) são incluídas nas regras de firewall. Verifique se que as portas TCP e UDP necessárias sejam abertas no firewall. Mídia prefere UDP sobre TCP. TCP é considerado um protocolo de failback.<br><ul><li>**TCP:** a porta 443</li><li>**UDP:** portas 3478 – 3481</li><ul> |
| Verifique se                | Utilize a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar a conectividade do edifício afetado ou sub-rede usando a função de verificação de conectividade.    |


### <a name="call-drop"></a>Recebimento de chamadas

Ao contrário de falhas de instalação chamada, não há nenhum código de motivo para indicar por que a chamada abandonada falhas ocorreu, o que torna difícil isolar uma causa raiz específica. Para melhor triagem chamadas capitular, use uma abordagem deduzida. Correção de quaisquer áreas de interesse para áudio, os clientes de aplicação de patch e orientando o uso de dispositivos de certificados para equipes e Skype for Business, você esperaria falhas de chamada queda para recusar.

#### <a name="call-drop-failures-overall"></a>Geral de falhas de recebimento de chamadas

Este relatório de gráfico exibe a quantidade total de fluxos de áudio, fluxos de áudio total ignorados, e a porcentagem de queda de fluxo total. Aponte para qualquer uma das colunas para exibir seus valores, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico mostrando a porcentagem de queda de fluxos de áudio de chamada](media/quality-of-experience-review-guide-image18.png)

_Figura 18 - chamada Total queda percentual de falha_

##### <a name="analysis"></a>Análise

Este relatório de gráfico exibe a falhas e o uso da sua organização ao longo do tempo relacionado ao chamar quedas. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a chamada atual de total queda porcentagem?

2.  É a porcentagem do total de depósito abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório podem saber a história da frequência suas geral quedas de chamada estão ocorrendo em toda a organização.

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. Embora a taxa geral de recebimento pode estar abaixo na métrica de destino, muitas vezes a taxa de recebimento de um ou mais redes ou prédios estiver acima na métrica e precisa remediação.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Falhas de recebimento de chamadas pela criação ou sub-rede

Falhas neste relatório de tabela indicam que a chamada foi interrompida inesperadamente e resultou em uma experiência de usuário negativo. Existem dois relatórios de tabela incluídos no modelo, um para investigar a conferência e outro para duas partes.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.


![Relatório que relaciona o número e a porcentagem de queda de chamadas, organizadas por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image19.png)

_Figura 19 – a chamada de áudio queda de falhas pela criação ou sub-rede_

##### <a name="remediation"></a>Remediação

Usando o relatório de tabela anterior, você pode isolar agora "pontos de acesso" na rede gerenciada onde quedas de chamada ocorrerem acima a métrica destino definida. Concentre os esforços de remediação em prédios ou redes que possuem a contagem de fluxo total mais alta primeiro, para tornar o maior impacto.

Causas comuns de quedas de chamada:

-   Saída de rede ou internet em provisionado

-   Nenhum QoS configurado em redes restritas

-   Versões mais antigas do cliente

-   Comportamento do usuário

Depois que você descobrir os pontos de acesso, você pode aproveitar a [Chamada análise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar ainda mais usuários em que construção para problemas específicos. Análise de chamada contém dados PII e pode ser útil para isolar ainda mais os motivos possíveis para a cai de chamada.

Independentemente da sua próxima etapa, é uma boa prática para notificar a helpdesk que foi descoberto um problema com os prédios específicos ou sub-redes. Dessa forma, rapidamente eles podem responder às chamadas recebidas e triagem usuários com mais eficiência. Usuários sinalizados, em seguida, podem ser informados volta para a equipe de engenharia para uma investigação detalhada.

A tabela a seguir lista alguns métodos comuns para gerenciar e remediar quedas de chamada.

_A tabela 9 - próximas etapas para chamada drop remediação_

| Remediação                              | Orientação     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rede/internet                         | Agora que você sabe qual construção é afetada, trabalhe com a equipe de rede para monitorar a largura de banda em que construção para determinar se há problemas com excesso. Se o problema for detectado estar relacionado ao congestionamento da rede, considere o aumento de largura de banda para essa construção. <br><br>**QoS:** Se o aumento da largura de banda é impossível ou caro, considere a implementação de QoS. Isso garantirá a pacotes de mídia na rede gerenciada são priorizados acima tráfego de mídia não. Como alternativa, se não houver nenhuma evidência clara que largura de banda é o responsável, considere estas soluções:<br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação. <br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra os [requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clientes (Skype para negócios apenas Online) | Alguns clientes mais antigos possuem conhecidos, documentados problemas com confiabilidade de mídia. Revise os relatórios de análise de chamada de vários usuários afetados ou crie um relatório de tabela de versão do cliente personalizado no CQD filtrado específicos prédios ou sub-redes com medida de % do Total de chamadas queda de falha. Essas informações ajudarão você a entender se existe uma relação entre quedas de chamada na que edifício específico e uma versão específica do cliente.                                                                                                                                                              |
| Dispositivos                                  | A maioria das falhas de dispositivo são devido ao uso de dispositivos que não são certificados para equipes ou Skype para negócios. Falhas normalmente assumem a forma do integrada de alto-falantes ou microfones que estão sendo usados ou combinações de earbud/microfone estão conectadas à tomada de áudio de 3,5 mm em um dispositivo. Recomendação de atual da Microsoft é que todos os usuários que estão enfrentando chamar quedas — ou ruins chama em geral — e estão usar dispositivos integrados ou drivers deve ser provisionado um [certificado headset ou viva-voz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamento do usuário                            | Se achar que nem rede, dispositivos ou clientes são o problema, considere o envolvimento do [Meu Advisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de adoção de usuário para instruir os usuários como práticas ingressar e sair de reuniões. As equipes de uma forma mais inteligente e Skype usuário produzirá uma melhor experiência de usuário para todos os participantes da reunião. Um usuário que coloca seus laptops em suspensão (fechando a tampa) sem sair da reunião será classificado como um depósito chamada inesperada.     |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade de áudio entre a implantação é investigar áudio ruim chamada proporção (PCR), TCP e uso de proxy. É importante lembrar que os dados CQD não fornecem uma causa raiz específica, mas fornece em vez disso, com áreas de problema provavelmente iniciar uma conversa de colaboração com as equipes apropriadas para atividades de correção.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="investigate-call-quality"></a>Investigar a qualidade da chamada

A porcentagem PCR geral é usada principalmente para indicar se a organização é reunião destinos de métricas de áudio definidos. É importante observar que, mesmo se a porcentagem geral estiver dentro de destino, alguns sub-redes ou prédios talvez não cumprir os objetivos definidos e, portanto, precisa as investigações. Por exemplo, se a porcentagem PCR áudio organizacional for % 3 em dezembro, que atende o destino de amostra, prédios específicos pode ainda ser tendo experiências ruins, dependendo da distribuição de que % 3.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentagem de chamadas ruins organizacional geral

Para avaliar a porcentagem geral de chamadas de baixa para a organização usar o relatório de gráfico de qualidade geral.

![Captura de tela de um gráfico mostrando a porcentagem de chamadas de baixa qualidade](media/quality-of-experience-review-guide-image20.png)

_Figura 20 – qualidade de áudio - geral_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe PCR e o uso da sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que podem precisar de mais investigação. Embora a PCR geral pode estar abaixo na métrica de destino, muitas vezes PCR para um ou mais prédios ou redes estiver acima na métrica e precisa ainda mais investigação.

#### <a name="audio-quality-overall"></a>Qualidade de áudio geral

Há duas árvores de relatório incluídas nos modelos de qualidade de áudio, um para investigar a conferência e outro para chamadas de duas partes. Para fins de remediação de qualidade, o processo de investigação é a mesma, portanto focaremos aqui na conferência. Melhorias na qualidade de conferência também positiva afetará a qualidade das chamadas de duas partes. Relatórios também são incluídos para exibir a qualidade de áudio para conferências e duas partes por com fio e Wi-Fi.

> [!NOTE]
> Investigar chamadas de baixa de duas partes é semelhante ao investigando chamadas em conferência. A tarefa é identificar prédios ou sub-redes que tenham a qualidade inferior para validar se houver um padrão de chamadas ruins com outra construção ou sub-rede. 

![Captura de tela da qualidade de áudio - relatório de conferência no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image21.png)

_Figura 21 – qualidade de áudio - conferência_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe a conferência da sua organização ou uso de dois participantes e PCR ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É PCR pior ou melhor do que o mês anterior?

4.  É a tendência PCR aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que talvez seja necessário investigação. Embora a PCR geral pode estar abaixo na métrica de destino, geralmente PCR para um ou mais prédios ou redes estiver acima na métrica e precisa remediação.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Fluxo de áudio ruim Construindo e sub-rede

Este relatório de tabela oferece compreensão adicional sobre o que contribuíram para as chamadas sendo classificada como pobre e ajuda a isolar os pontos de acesso da rede gerenciada.

Os detalhes de conexão distingue com fio e Wi-Fi e inclui as medições de tempo de ida e volta (tempo de resposta), perda de pacote e Tremulação. Um relatório semelhante também existe sob os relatórios de duas partes e é usado para isolar as chamadas de duas partes em sua rede gerenciada.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão. 

> [!TIP]
> Redes domésticas comuns são difíceis de triagem devido ao seu uso amplo. Foi adicionado um relatório separado que usa o IP do firewall para o modelo de todas as redes para auxiliar com escritórios remediando que usam redes comuns.

![Relatório que lista os tipos de conexão, tipos de transporte e PCR maior que 3%, juntamente com várias finalidades de baixa qualidade organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image22.png)

_Figura 22 - resumo de fluxo de áudio ruim, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Concentrar os esforços de remediação em prédios ou redes que possuem o maior volume de fluxos de áudio, pois isso maximizar o impacto e ajudar a melhorar o usuário experimentam rapidamente. Use a tremulação, perda de pacotes e medidas de tempo de resposta para compreender o que está contribuindo para a qualidade da chamada ruim. É possível para ter mais de um problema:

-   **Tremulação:** Pacotes de mídia chegam ao velocidades diferentes, o que faz com que um alto-falante som robótica.

-   **Perda de pacotes:** Pacotes de mídia estão sendo eliminados, que cria o efeito das palavras ou sílabas faltando.

-   **Tempo de resposta:** Pacotes de mídia estão demorando muito tempo para chegar ao seu destino, que cria um efeito de walkie-talkie.

Embora nenhuma fonte única de veracidade contas para o que pode causar uma chamada de baixa, vários métodos comuns podem ajudá-lo a lidar com problemas de rede.

Para auxiliar sua investigação sobre problemas de qualidade, você pode aproveitar a [Análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Com a análise de chamada, você pode examinar uma conferência específica ou relatório de chamada detalhada dos usuários. Este relatório conterá os dados PII e é útil quando tentar distinguir um motivo para falhas. Quando você souber qual edifício é afetado, rastreamento de usuários em que a construção deve ser simples.

Não se esqueça de informar a helpdesk que essas redes estão enfrentando problemas de qualidade, para que possam rapidamente triagem e responder às chamadas recebidas.

_A tabela 9 - comuns Contribuidores PCR alta_

| Remediação                              | Orientação       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Uma rede com uso excessivo ou em provisionado pode causar problemas com a qualidade de mídia. Trabalho com a equipe de rede para determinar se as conexões de rede do usuário até a saída de internet apontam tem largura de banda suficiente para oferecer suporte a mídia. **Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação.<br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. Essa ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra as de desempenho do Microsoft [requisitos](https://aka.ms/performancerequirements).<br><ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Qualidade de serviço (QoS)                 | QoS é um método comprovado para ajudar a priorizar pacotes em uma rede para garantir que eles cheguem a seu destino intacto e no tempo. Considere a implementação de QoS em toda a organização para maximizar a qualidade da experiência do usuário onde a largura de banda é limitada ou restrita. QoS ajudarão a solucionar problemas normalmente associados a altos níveis de perda de pacotes, e — a um grau menor — tempos de tremulação e de ida e volta. <br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi pode ter um impacto significativo sobre a qualidade da chamada. Design de Wi-Fi não terá normalmente em consideração os requisitos de rede para serviços de VoIP e, geralmente, é uma fonte de baixa qualidade. **QoS:** Redes sem fio modernos devem oferecer suporte a vários dispositivos. Esses dispositivos competem por largura de banda e podem causar problemas de qualidade para serviços de VoIP onde estão vitais velocidade e a latência. Consulte seu fornecedor de sem fio para obter informações específicas e considere a implementação de QoS em sua rede sem fio priorizar Skype para negócios e equipes de mídia. **Densidade AP:** Pontos de acesso (pontos de acesso) podem ser muito distantes ou não em um local ideal. Para minimizar a interferência potencial, coloque extras pontos de acesso em salas de conferência e em locais que não são obstruídos por paredes ou outros objetos. **2,4 GHz versus 5 GHz:** 5 GHz fornece menos interferência de plano de fundo e as velocidades maiores e devem ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não entrar na paredes tão facilmente. Examine seu layout de construção para determinar qual frequência você pode depender para a conexão recomendada. **Intensidade do sinal:** Em geral, medido em dBm (taxa de alimentação em decibéis), mede a intensidade do sinal sem fio. Depois que um dispositivo está conectado a um ponto de acesso, ele não quer permitir que vá facilmente. Como o dispositivo se move para fora do ponto de acesso, a intensidade do sinal cai para um ponto que induz uma conexão ruim, mesmo que a outra, quanto mais perto AP está disponível. Se possível, trabalhe com seu fornecedor de AP para garantir que os pontos de acesso estão configurados para descartar um dispositivo quando a intensidade do sinal fica abaixo de um nível aceitável. Isso garantirá que o dispositivo não congele um PA fraca. Isso é uma boa solução quando você não pode adicionar facilmente mais pontos de acesso. **Driver wireless:** Quando tudo mais falhar, certifique-se de que os drivers sem fio estão atualizados. Isso ajudará a atenuar qualquer experiência de usuário ruim relacionada a um driver desatualizado. |
| Dispositivo de rede                           | Organizações maiores podem ter centenas de dispositivos afastadas através da rede. Trabalho com a sua equipe de rede para garantir que os dispositivos de rede do usuário para a internet são mantidos e atualizados.     |
| VPN                                      | Ele foi bem documentado que aparelhos VPN tradicionalmente não são projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferido para áudio) e contam com apenas TCP. Considere a implementação de uma [solução de divisão de túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ajudar a reduzir a VPN como uma fonte de baixa qualidade.        |
| Clientes (Skype para negócios apenas Online) | Clientes mais antigos são conhecidos por causar problemas com a mídia. Certifique-se de que os clientes estão sendo patch dentro de seis meses após o lançamento. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de cliente e deploy [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | O uso de [dispositivos de otimizado](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pode ajudar a melhorar significativamente a experiência do usuário. Com todas as coisas sendo igual, dispositivos otimizados foram projetados para maximizar a experiência do usuário com equipes e Skype para negócios e produzir qualidade superior. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar sessões de áudio de TCP

TCP é considerado um transporte failback e não o transporte principal que você deseja para a mídia em tempo real. Isso é um transporte failback é devido à natureza do TCP com informações de estado. Por exemplo, se uma chamada for feita em uma rede latente e pacotes de mídia estão atrasados, em seguida, os pacotes de alguns segundos atrás — que não são mais úteis — competem por largura de banda chegar ao destinatário, que pode tornar um pior situação ruim. Isso torna o stitch de correção de áudio e áudio Alongar, resultando em artefatos audíveis geralmente na forma de tremulação.

Os relatórios nesta seção não fizer uma distinção entre chamadas boas e ruins. Visto que UDP é o preferido, os relatórios procuram o uso de TCP para áudio. Isso é principalmente causado pelas regras de firewall incompleta. Para obter mais informações sobre regras de firewall para equipes e Skype para Business Online, consulte [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Fluxos de áudio com o uso TCP geral

Este relatório indica o uso geral de TCP para áudio nos últimos sete meses, conforme mostrado abaixo.

Todos os relatórios mais nesta seção abordará estreitando pressionada prédios específicos e sub-redes onde o TCP é usado com mais frequência. Mais sub-relatórios romper o uso TCP por conferência e chamadas de duas partes.

![Captura de tela de um gráfico mostrando o número de fluxos de áudio de TCP por mês](media/quality-of-experience-review-guide-image23.png)

_Figura 23 – fluxos de áudio com o uso TCP_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe o uso TCP geral da sua organização. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é o volume total de chamadas TCP para o mês atual?

2.  É melhor do que o mês anterior ou de pior?

3.  É a tendência de uso do TCP aumentando, steady, ou diminuindo?

Se notar que a tendência de uso do TCP está aumentando ou acima de utilização monthly normal, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. O ideal é que você deseja, no mínimo com base em TCP sessões de áudio possível na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Este relatório de tabela identifica o volume de TCP versus relatórios sobre o mês mais recente para conferências de áudio, vídeo e vídeo-based (VBSS) de compartilhamento de tela de uso do UDP.

![Relatório mostrando o volume de TCP versus fluxos de conferência UDP, com PCR mostrado na comparação](media/quality-of-experience-review-guide-image24.png)

_Figura 24 – TCP versus UDP - conferência_

##### <a name="analysis"></a>Análise

Embora você deseja o uso TCP ao ser tão baixa quanto possível, talvez você veja um pouco de uso TCP em uma implantação do contrário íntegro. Para comparar UDP com o uso TCP, divida fluxos de áudio de TCP por fluxos de áudio de UDP para determinar uma porcentagem. Um valor de mais de 1% precisa ser investigados ainda mais.

No exemplo acima, pegamos 1,806 fluxos TCP divididos por 10,481 fluxos UDP chegar a um valor de 17.2%. Esse valor é bem acima % 1 e nos diz que precisamos continuar nossa investigação para determinar onde o uso TCP está ocorrendo.

Também é incluída no relatório é a porcentagem de áudio ruim. Isso proporciona um modo de exibição para a comparação de qualidade da chamada entre UDP e TCP para ajudar a visualizar como TCP está afetando a qualidade da chamada overcall.

Então agora que você determinou que não há um alto uso de áudio com base em TCP em sua organização, o que fazer em seguida? Vá para os relatórios de **fluxos TCP Construindo e sub-rede** para dividir o uso TCP pelo construção e sub-redes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Fluxos TCP Construindo e sub-rede

Nos modelos de CQD fornecidos, vá para os fluxos TCP por sub-rede e criação de relatórios de tabela usando o gerenciada ou modelo de todas as redes. Há três relatórios incluídos no modelo, um para investigando conferência, com e sem informações de retransmissão da Microsoft e outro para investigando chamadas de duas partes. Para fins de investigar o uso TCP, o processo é a mesma, portanto focaremos a discussão na conferência somente.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                                  |

![Relatório que lista os fluxos TCP, organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image25.png)

_Figura 25 – TCP fluxos, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o volume de uso do TCP. Um relatório adicional também está incluído para identificar o IP de retransmissão Microsoft que foi usado na chamada para ajudar a isolar ausentes regras de firewall. Concentre os esforços de remediação nesses prédios que têm o maior volume de fluxos de áudio para maximizar o impacto.

A causa mais comum de uso do TCP está faltando regras de exceção no firewalls ou proxies. Voltaremos falando proxies na próxima seção, portanto por enquanto concentrar os esforços nos firewalls. Usando o edifício ou sub-rede fornecido, você pode determinar o firewall que precisa ser atualizado.

_Tabela 10 - remediação * orientação para fluxos TCP Construindo e sub-rede_

| Remediação        | Orientação     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar o firewall | Verifique se [as portas de IP do Office 365 e endereços](https://aka.ms/o365ips) são excluídos do seu firewall. Embora haja muitos endereços IP e portas que precisam ser aberto, problemas relacionados a mídia TCP, concentrar os esforços iniciais no seguinte: Verifique se as seguintes [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) estão em suas regras de firewall. Referir-se a linha 4 na tabela mostrada para obter informações de sub-rede de mídia específicos. [As portas UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): essas portas são as portas de mídia preferencial e devem ser abertas, caso contrário, o cliente falhará volta para a porta TCP 443. |
| Verifique se             | Use a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas de conectividade para portas e endereços IP do Office 365 específicos do edifício afetado ou sub-rede.    |

### <a name="investigate-http-proxy-usage"></a>Investigue o uso do proxy HTTP

Os proxies HTTP não é o caminho preferido para estabelecer sessões de mídia, para uma infinidade de motivos. Muitas contêm recursos de inspeção de pacotes profunda que pode impedir conexões ao serviço sejam concluídas e introduzir interrupções causadas. Além disso, os proxies talvez forçar TCP em vez de permitindo UDP, que é recomendado para melhor qualidade de áudio.

É sempre a recomendação da Microsoft para configurar o cliente para conectar-se diretamente a equipes e Skype para serviços corporativos. Isso é especialmente importante para o tráfego de mídia-based.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Fluxos de áudio com o uso de proxy HTTP geral

Este relatório descreve o uso de proxy ao longo do tempo em uma escala mensal. O relatório de fluxo de proxy HTTP nesta seção do modelo é muito semelhante os relatórios TCP. Ele não parece estar em estejam de chamadas ruins ou BOM, mas se a chamada é conectada por HTTP.

![Captura de tela dos fluxos de áudio com o relatório de uso do Proxy HTTP no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image26.png)

_Figura 26 – fluxos de áudio com o uso de Proxy HTTP_

##### <a name="analysis"></a>Análise

Se você vir um alto volume de uso do HTTP, consulte sua equipe da rede para garantir que as exclusões adequadas estejam em vigor para que os clientes são roteamento diretamente para equipes ou Skype para sub-redes de mídia Business Online. Idealmente, não deve haver nenhum uso do HTTP exibido aqui.

Se você tiver apenas um proxy de internet em sua organização, verifique as adequadas [URLs do Office 365 e exclusões de intervalo de endereços IP](https://aka.ms/o365ips). Se mais de um proxy de internet está configurado em sua organização, aproveitar o HTTP sub-recursos relatado para isolar qual construção ou sub-rede é afetado.

Para organizações que não é possível ignorar o proxy, certifique-se que o Skype para o cliente de negócios está configurado para entrar em corretamente quando ela está localizada atrás de um proxy conforme descrito no artigo [Skype para negócios deve usar servidor proxy para entrar em vez de tentar direta conexão](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Fluxos de proxy HTTP Construindo e sub-rede

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o uso do HTTP.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                        |

![Captura de tela do uso do Proxy HTTP pelo relatório de criação e a sub-rede em que o painel de controle de qualidade de chamada.](media/quality-of-experience-review-guide-image27.png)

_Figura 27 – sub-rede e uso de Proxy HTTP, criando_

##### <a name="remediation"></a>Remediação

Concentre os esforços de remediação em qualquer prédios ou as sub-redes com o uso de proxy HTTP. A causa mais comum de uso do HTTP está faltando regras de exceção de proxies. Usando o edifício ou sub-rede fornecido, você pode determinar qual proxy precisa ser atualizado.

Verifique se os [FQDNs do Office 365](https://aka.ms/o365ips) de necessários são excluídos do seu proxy.

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção se concentra nas tarefas de relatórios sobre o Skype para versões do cliente de negócios – específicas e o uso de dispositivos de certificados.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="determine-client-versions"></a>Determinar as versões do cliente

O relatório neste espaço enfoca identificando Skype para versões do cliente de negócios em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio de rede conteúdo de entrega Azure (CDN) e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.

Números de versão do Skype para negócios 2015 e 2016 podem ser encontrados por meio de links a seguir:

-   [Liberações de canal de atualização de cliente Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versão e compilação do Office 365 para clique para executar](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para downloads de negócios e atualizações](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.  

> [!IMPORTANT]
> Relatórios de cliente exigem que você excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. |

![Captura de tela do relatório de cliente e dispositivos no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image28.png)

_Figura 28 - relatório da versão de cliente_

#### <a name="remediation"></a>Remediação

Uma parte importante de dirigir experiências do usuário de alta qualidade é garantir que os clientes de gerenciada estão executando versões atualizadas do Skype para negócios. Isso oferece vários benefícios, entre eles:

-   É mais fácil gerenciar algumas versões versus muitas versões.

-   Ele fornece um nível de consistência da experiência.

-   Ele facilita a solucionar problemas de qualidade de chamada e usabilidade.

-   A Microsoft dá continuamente aperfeiçoamentos gerais e as otimizações em todo o produto. Garantir que os usuários recebam essas atualizações reduz os riscos de executar um problema que já foi resolvido.

Limitar sua implantação para as versões do cliente que são menos de seis meses, melhorar a experiência geral do usuário e melhorar a capacidade de gerenciamento em comparação a ter grandes números de diferentes versões do cliente no mesmo ambiente.

Se você estiver usando somente Office Click-to-Run, você estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional será necessária.

If, como a maioria das organizações, você tem uma mistura de pacotes Click-to-Run e installer (MSI), você pode usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Concentre seus esforços nesses clientes onde o volume está acima da média. Se você observar que os clientes são atrasado, trabalhar com a equipe responsável pelo gerenciamento de atualizações do Office e garantir que eles estiver aprovando e Implantando patches de cliente regularmente.

### <a name="devices-investigations"></a>Investigações de dispositivos

Para tornar use destes relatórios dispositivo, é melhor entender o conceito de médio de opinião pontuação (MOS). MOS é a medida padrão ouro para medir a qualidade de áudio perceptivelmente. Ele é representado como uma classificação de inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade de voz. Como ela é afetada pela percepção humana, é naturalmente subjetiva. Existem várias metodologias diferentes para testar subjetiva.
A maioria das medidas de qualidade de voz são baseados em uma escala de classificação (ACR) categorização absoluta.

Em um teste subjetivo ACR, um número significativo de estatística de pessoas classificar seu qualidade da experiência em uma escala de 1 (ruim) a 5 (excelente). A média das pontuações é o MOS. O MOS resultante depende do intervalo de experiências que foram expostos ao grupo e ao tipo de experiência sendo classificada como.

Porque ele é impraticável para conduzir testes subjetivas de qualidade de voz para um sistema de comunicação em tempo real, equipes e Skype para negócios geram valores MOS usando algoritmos avançados objetivamente prever os resultados de um teste subjetiva.

O conjunto disponível de MOS e métricas associadas fornecem um modo de exibição para a qualidade da experiência de ser entregue aos usuários.

Fornecendo aos usuários com dispositivos certificados para equipes e Skype for Business, você reduz a probabilidade de encontrando experiências negativas devido ao próprio dispositivo (que é mais provável, por exemplo, com microfones e alto-falantes laptop internas). Para obter mais informações, consulte [telefones e dispositivos para Skype para negócios](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso organizacional dos dispositivos de captura (microfones) por volume

Este relatório é usado para avaliar o uso de microfone por volume e de pontuação do MOS e pode ser encontrado nos modelos acompanha em clientes e dispositivos *.*

> [!IMPORTANT]
> Relatórios de dispositivo exigem que você poderá excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. 

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.<br><br> Você poderá observar quando visualizem esse relatório que você veja o mesmo dispositivo relatado várias vezes. Isso acontece devido à maneira como o dispositivo é informado de serem reportados para CQD. Diferenças de hardware e de localidade do sistema operacional relatar dados do dispositivo de forma diferente.

![Captura de tela do relatório de dispositivos (microfone) no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – relatório de dispositivo (microfone)_

##### <a name="remediation"></a>Remediação

A primeira tarefa é determinar o alvo de MOS que você gostaria de obter. Intervalo de 1 a 5, com 5 sendo o melhor de pontuações MOS. Escolha um destino razoável, com base em seu ambiente e os resultados da consulta. No exemplo a seguir, o destino será uma pontuação do MOS de 3.6 ou superior para todos os dispositivos que tenham mais de 100 fluxos. Você obterá a qualidade do dispositivo de destino quando:

-   Os resultados da consulta de dispositivo retornam MOS \> 3.6 para NumStreams \> 100

Normalmente, você precisará substituir dispositivos com desempenho insatisfatório por dispositivos de certificados. Algumas considerações quando analisando o relatório de dispositivo incluem:

-   São dispositivos certificados ou conhecidos para ser boas em seu ambiente? Se um dispositivo de certificados ou boa é retornado na consulta com uma pontuação do MOS inferior que sua linha de base, pode haver desconhecidos fatores adicionais (por exemplo, uma rede ruim ou pc capacidade suficiente) que está contribuindo para a pontuação baixa.
    Investigação adicional será necessária.

-   Você pode identificar os usuários de um dispositivo por meio da [Análise de chamada](#call-analytics-training). Verifique para garantir que eles têm os drivers de dispositivo mais recentes e que seu dispositivo não está conectado por meio de um hub USB.

-   Verificar se há uma correlação entre dispositivos ruim e tornar um determinado do sistema e modelo. Em caso afirmativo, o dispositivo talvez não seja compatível ou precisa de atualizações de driver.

A segunda tarefa é determinar o uso geral de dispositivos não-certificados. É recomendável que pelo menos de 80 por cento de todos os fluxos de áudio de usar um dispositivo de certificados.
Isso é realizado melhor exportando o relatório de dispositivos para o Excel e manualmente Calculando o uso de dispositivos de certificados ou aprovados. As organizações geralmente manter uma lista de todos os dispositivos aprovados, para que filtragem e classificação dos dados devem ser simples.

## <a name="appendix-a-lync-networking-guide"></a>Guia de rede do apêndice Lync r.

Para obter mais informações em equipes e Skype para conceitos de rede de negócios e o raciocínio por trás de sua importância a qualidade, o [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) é aplicável.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de desempenho do apêndice B. rede

A qualidade de mídia em tempo real (áudio, vídeo e compartilhamento de aplicativos) sobre IP significativamente é afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter melhor equipes ou Skype para qualidade de mídia de negócios, sua rede deve atender aos seguintes métricas de desempenho de rede.

_A tabela 11 - requisitos de desempenho de rede_

| Métrica                           | Cliente para o Microsoft Edge           | Edge do cliente para o Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latência (uma maneira)                | \<50 ms                            | \<30 ms                            |
| Latência (tempo de resposta ou tempo de ida e volta) | \<100 ms                           | \<60 ms                            |
| Perda de pacotes de intermitência                | \<10% durante qualquer intervalo de 200 ms   | \<1% durante qualquer intervalo de 200 ms    |
| Perda de pacote                      | \<1% durante qualquer intervalo de 15 segundos    | \<0,1% durante qualquer intervalo de 15 segundos  |
| Tremulação de entre chegada de pacotes      | \<30 ms durante qualquer intervalo de 15 segundos | \<15 ms durante qualquer intervalo de 15 segundos |
| Reordenar de pacotes                   | \<% de 0,05 pacotes de fora de ordem       | \<pacotes de fora de ordem 0,01%      |

Para obter mais informações, consulte o artigo a seguir sobre o [desempenho de rede e qualidade de mídia](https://aka.ms/performancerequirements) para equipes e Skype para negócios Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apêndice C. Outros recursos

### <a name="building-data-file"></a>Criando o arquivo de dados

-   [Ativando e usar CQD no Skype para negócios Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Treinamento de CQD

-   <https://aka.ms/sof-cqd>

-   Guia de [Introdução ao CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) e workshop.

-   [Guia on-line CQD dimensões e medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Treinamento de análise de chamada

-   [Apresentando a análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar a Análise de Chamada do Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Qual é a diferença entre a Análise de Chamada e o Painel de Qualidade de Chamadas?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas no Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Suporte de análise de chamada

-   Comunidade: [Skype para o programa de visualização de negócios](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Para obter suporte, entrar em nosso portal de visualização [www.skypepreview.com](http://www.skypepreview.com), selecione **um problema de relatório**e usar a opção **Criar novo Bug** para relatar algum problema. Observe que os engenheiros de suporte estão disponíveis para oferecer suporte de segunda à sexta-feira, entre os horários de 6 horas para 9 PM EST. Solicitações fora essas horas serão priorizadas do dia seguinte.

### <a name="devices"></a>Dispositivos

-   [Skype para soluções de negócios pessoais periféricos & PCs de catálogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Relatórios de locatário

-   [Pacote de conteúdo de adoção do Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Relatórios do Skype for Business Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Relatórios de Teams da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
    =======
---
title: Qualidade da experiência Revise o guia para equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guia para analisar o desempenho de mídia em tempo real for Microsoft Teams usando o painel de controle de qualidade de chamada (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
  - Microsoft Teams
---

# <a name="quality-of-experience-review-guide"></a>Qualidade da experiência Revise o guia

Este guia é sobre a fase de unidade de valor para o Microsoft Teams e Skype para negócios Online. Você pode [baixar uma versão do Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) deste guia.

## <a name="introduction"></a>Introdução

Para que o maior impacto sobre como melhorar a experiência do usuário, as organizações precisam tornem operacional as principais áreas que são mostradas na figura a seguir.
Áreas adicionais incluem identificando tarefas operacionais, estabelecimento de metas para métricas de qualidade, averiguar as métricas usar para medir o êxito organizacional e estreitando áreas de investigação conforme necessário.

![Principais áreas para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuário, dispositivos e clientes.](media/quality-of-experience-review-guide-image1.png)

_Figura 1 - operacionais áreas de chave abordadas neste documento_

Continuamente avaliando e correção as áreas descritas neste documento, você pode reduzir seu potencial para afetar negativamente a qualidade da experiência dos usuários. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta

-   Baixa cobertura de Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Versões do cliente inconsistentes ou desatualizadas

-   Dispositivos de áudio não otimizados ou internos

-   Sub-redes problemáticos ou dispositivos de rede

Através de planejamento adequado e design antes de implantar equipes ou Skype para Business Online, você pode reduzir a quantidade de esforço que serão necessários para manter experiências de alta qualidade.

Este guia se concentra no uso do Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área, com uma ênfase especial para maximizar a adoção e o impacto de áudio. Todos os aprimoramentos feitos à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

Para acelerar sua avaliação, dois modelos CQD curated são fornecidos: um para o gerenciamento de todas as redes e o outro fosse filtrada para gerenciados apenas as redes (internas). Embora os relatórios de modelo de todas as redes são configurados para exibir informações de rede e de construção, ele ainda pode ser usado enquanto você trabalha em direção a coleta e carregamento de informações de construção. Carregar informações em CQD do edifício habilita o serviço aperfeiçoar os relatórios adicionando informações personalizadas de construção, rede e local enquanto distinguir interna do sub-redes externos. Para obter mais informações, consulte [mapeamento de construção](#building-mapping) posteriormente neste documento.

### <a name="what-is-the-cqd"></a>Qual é o CQD?

Use o painel de qualidade de chamada (CQD) para obtém ideias sobre a qualidade das chamadas feitas por meio de equipes e Skype para serviços corporativos. CQD foi projetado para ajudar Skype para os administradores corporativos e as equipes e os engenheiros de rede otimização a rede. CQD analisa agregam informações para uma organização inteira onde padrões gerais podem se tornar aparentes, permitindo que a equipe efetue informadas avaliações de qualidade de chamada. CQD fornece relatórios de métricas de chamada que lhe dão ideia da experiência do usuário, confiabilidade de chamada e qualidade geral da chamada.

> [!NOTE]
> CQD não contém informações de identificação pessoal (PII). PII é informações que podem ser usadas por conta própria ou com outras informações para identificar, entre em contato ou localizar uma única pessoa ou para identificar um indivíduo em contexto. 

### <a name="intended-audience"></a>Público-alvo

Este documento é destinado a ser usado pelo parceiro e cliente participantes com funções como arquiteto/líder de colaboração, consultor, especialista da adoção do gerenciamento de alteração, ajuda/suporte de liderança de mesa, liderança de rede, liderança de área de trabalho e administrador de TI.

Este documento também se destina a ser usado pelo champion(s) a qualidade designada.
Para obter mais informações, consulte [a função campeão de qualidade](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este guia, verifique se que você tem as [funções](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) de locatário adequadas atribuído para que você possa acessar CQD.

-   **Função Administrador Global do office 365:** Acessa todos os recursos administrativos no conjunto do Office 365 de serviços em seu plano, incluindo Skype para negócios.

-   **Skype para a função de administrador de negócios:** Configura Skype for Business para sua organização e é capaz de exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365. Essa função é necessária, mesmo se você implantar apenas equipes.

Como alternativa, você pode atribuir a função a seguir para uma conta de usuário do Office 365 deseja permitir acesso a somente os recursos de relatório.

-   **Relata leitor:** Pode exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365, qualquer relatórios do [pacote de conteúdo do Office 365 adoção](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e relatórios CQD.

Noções básicas sobre os principais conceitos do CQD ajuda a maximizar o impacto que você pode fazer em melhorar a experiência de seus usuários com equipes ou Skype para Business Online.
Recursos adicionais podem ser encontrados no [Apêndice](#other-resources).

## <a name="what-is-quality"></a>Qual é a qualidade?

Ao discutir qualidade em equipes e Skype para os negócios, é importante definir o termo para atingir um entendimento comum. A qualidade, conforme definido aqui, é uma combinação de serviço métricas e experiência do usuário.

![Métricas de serviço são compostas das versões de chamadas ruins proporção, confiabilidade, pontos de extremidade/dispositivos e cliente. Experiência do usuário final é formada pelo percepção do usuário da qualidade de serviço.](media/quality-of-experience-review-guide-image2.png)

_Figura 2: o que há de qualidade?_

### <a name="define-your-target-metrics"></a>Definir seus métricas de destino

Esta seção discute as métricas de serviço principal que usamos para avaliar como serviços apresentem integridade. Continuamente avaliando e orientando os esforços para manter essas métricas abaixo de destino, você vai ajudar a garantir a que qualidade da chamada uniforme e confiável de experiência de seus usuários. Para começar, as metas a seguintes são fornecidas.
Vamos resumem a diferença entre uma rede gerenciada e:

-   Uma rede *gerenciados* pode ser influenciada e controlada pela organização.
    Isso inclui LAN interna, WAN remoto e VPN.

-   Uma rede *não gerenciada* não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de hotel ou aeroporto.

_Tabela 1 - métricas de avaliação de integridade de destino principais_

|               | Qualidade para redes gerenciadas | Confiabilidade para redes gerenciadas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nome de métrica   | % De taxa de chamada de áudio inválida      | Configuração da chamada % de falhas            | Recebimento de chamadas % de falhas |
| Destino da amostra | \<% 3                         | \<% 1                             | \<4%                 |

É importante discutir e definir as metas da sua organização para atender aos seus objetivos de negócios. Idealmente, você deve identificar nestes destinos antes da implantação.

#### <a name="audio-pcr-"></a>% De áudio PCR 

Áudio ruim chamada proporção (PCR) representa a porcentagem geral da organização de chamadas que têm má qualidade de áudio. Essa métrica destina-se para realçar áreas onde sua organização pode se concentrar esforço para ter um impacto mais forte em direção a redução desse valor e aprimorando a experiência do usuário, o motivo pelo qual o foco principal são as redes gerenciadas ao olhar PCR. Os usuários externos são muito importantes, mas difere de investigações em uma base organizacional e de usuário.
Considerar o fornecimento de práticas recomendadas para usuários externos e examine efetuar chamadas externas independentemente do geral da empresa.

#### <a name="call-setup-failures-"></a>Configuração da chamada % de falhas 

Isso representa qualquer sessão de mídia que não pôde ser estabelecida. Devido a gravidade do impacto sobre a experiência do usuário medida aqui, o objetivo é reduzir este valor como como próximos de zero possível. Um valor alto para essa métrica é mais comuns em novas implantações com regras de firewall incompleto do que uma implantação desenvolvido, mas ainda é importante observar regularmente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

#### <a name="call-drop-failures-"></a>Recebimento de chamadas % de falhas 

Isso se aplica a uma carga de trabalho de áudio em que a sessão terminou inesperadamente. Conforme sua rigor operacional for envelhecendo, você poderá expandir essa métrica para incluir as cargas de trabalho de vídeos e compartilhamento de área de trabalho.

### <a name="service-metrics"></a>Métricas de serviço

Destinos de métricas de serviço consistem em métricas específicas baseados no cliente.

#### <a name="pcr"></a>PCR

A base para determinar se uma chamada foi classificada como ruim é usando a proporção de chamadas ruins (PCR). PCR é formada pelas métricas de rede cinco descritas na tabela a seguir. Para uma chamada para ser classificadas como insatisfatória, apenas uma métrica deve exceder o limite definido. Para obter mais informações sobre o processo de classificação de chamada, consulte [esta postagem de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabela 2 - métricas de serviço de chamadas ruins_

| Métrica                                           | Descrição                                                                                                                                                                                                                                                                                                                                                                  | Experiência do usuário                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tremulação \>30 ms                                   | Esta é a média alteração em atraso entre pacotes sucessivos. Equipes e Skype para negócios podem se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante avisos os efeitos de variação.                                                                                                                         | Os pacotes que chegam em diferentes velocidades causarão voz do alto-falante som robótica.                                                                                       |
| Taxa de perda de pacote \>10% ou 0,1                    | Geralmente, isso é definido como uma porcentagem dos pacotes que são perdidos. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos que têm quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.                                                                                                                               | Os pacotes sendo capitular e não chegada a seu destino pretendido causarão lacunas na mídia, resultando em palavras e sílabas perdidas e entrecortada vídeos e compartilhamento. |
| Tempo de ida e volta \>500 ms                         | Este é o tempo que leva para obter um pacote IP do ponto A ponto b e voltar para a ponto. Esse atraso de propagação de rede é associado à distância física entre os dois pontos e a velocidade da luz e inclui uma sobrecarga adicional tomada por vários dispositivos no caminho de rede.                                                                                  | Os pacotes demorando muito para chegar ao seu destino causam um efeito de walkie-talkie.                                                                                 |
| Média de degradação NMOS \> 1.0                  | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, juntos causado a rede [Pontuação média de opinião](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) para soltar por mais de um ponto. Isso não necessariamente significa que a conexão de rede estiver baixa, mas suficiente problemas ocorreram durante a chamada que qualidade foi reduzida. | Isso é uma combinação de tremulação, perda de pacotes, e — a um grau menor — aumento do tempo de ida e volta. O usuário pode estar apresentando uma combinação desses sintomas.          |
| Taxa média de amostras escondidas \> 7% ou 0,07 | Uma ou mais destas métricas de rede, embora individualmente não foram ruim, causou o cliente auto-restauração a mídia. Uma amostra de áudio escondida é uma técnica costumava suave check-out a transição repentina que geralmente seria causada por pacotes de rede capitular.                                                                                                                | Valores altos indicam que significativo níveis de ocultação perda foram aplicados e resultou em áudio distorcido ou perdido.                                                  |

#### <a name="client-and-device-readiness"></a>Preparação de clientes e dispositivos

Você precisa de uma estratégia sólida de clientes e dispositivos para garantir que os usuários tenham uma experiência de usuário consistente e positivo. Cada estratégia de preparação de unidade de alguns princípios-chave.

##### <a name="client-readiness"></a>Preparação do cliente

Uma estratégia de preparação de cliente forte garante que os usuários estão executando a versão mais recente do cliente ao mesmo tempo aproveitando a melhor experiência possível.
Microsoft rotineiramente patches do Skype para clientes corporativos; garantir que você o mantenha atualizado em seu ambiente é vital para o sucesso geral.

Recomendamos que você não permita que as versões de cliente se encaixam por mais de seis meses. Se você estiver usando o Office Click-to-Run, você estiver já sendo mantidos atualizados pelo serviço. Use o [Relatório de cliente](#determine-client-versions)incluídos, conforme descrito mais adiante neste guia, para ajudá-lo com esse processo. Você também pode aproveitar os relatórios de exemplo de taxa Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de cliente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


##### <a name="device-readiness"></a>Preparação de dispositivo

Sem uma estratégia de única pode afetar a experiência do usuário mais de sua estratégia de preparação de dispositivo. A maioria das organizações são feliz remover dispositivos desnecessários de usuários (por exemplo, telefones de mesa ou outros dispositivos de áudio dedicados), e isso é geralmente uma justificativa comercial de núcleo para alternar para equipes ou Skype para negócios. No entanto, dessas organizações mesmas às vezes hesite para fornecer dispositivos de substituição, mesmo se esses dispositivos são baratos. Moderna laptops e PCs, porém equipados com interna microfone e alto-falante, não são otimizadas para empresarial voz sobre IP (VoIP). Isso geralmente cria uma experiência ruim para todos os participantes, especialmente se o alto-falante está em um ambiente com ruído. Programa de certificação da Microsoft dispositivo garante que, quando um usuário participa de uma chamada telefônica usando qualquer dispositivo certificado para equipes ou Skype for Business, ele produzirá uma experiência que é superior a usar um dispositivo não certificados.

Sempre, recomendamos que equipes e Skype para usuários comerciais usam um fone de ouvido certified ou alto-falante ao participar de uma chamada de voz usando um cliente de desktop.
Para obter mais informações sobre dispositivos de certificados da Microsoft, revise neste [artigo sobre como telefones e dispositivos qualificados](https://technet.microsoft.com/office/dn788944.aspx). Use o [Device Report](#devices-investigations), posteriormente neste guia, para obter ajuda com o gerenciamento de seus dispositivos. Também, você pode usar os relatórios de exemplo de taxa de Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de dispositivo.

### <a name="user-experience"></a>Experiência do usuário

Analisando a experiência do usuário é mais arte do que ciência, porque as métricas coletadas aqui sempre não significa que há um problema com a rede ou serviço, mas em vez disso, eles indicam que o usuário percebe um problema. A Microsoft oferece um mecanismo de pesquisa interno — conhecido como taxa meu chamada (RMC) — para ajudar a estimar a experiência geral do usuário. RMC ajudarão você a responder às seguintes perguntas da perspectiva dos usuários:

-   Saber como usar a solução?

-   É a solução fáceis de usar e intuitiva e oferece suporte a minhas necessidades de comunicação diárias?

-   A solução Ajude-me trabalho?

-   Qual é a minha percepção geral da solução?

-   Posso usar a solução em qualquer ponto no tempo, independentemente de onde estou?

-   É possível configurar e manter uma chamada?

#### <a name="rmc"></a>RMC

RMC compilado no equipes e Skype para negócios e é automaticamente configurado para ser exibida depois que um em cada 10 chamadas ou 10% de todas as chamadas. Este breve pesquisa pede ao usuário classificar a chamada e fornecer um contexto de pouca para por que a qualidade da chamada pode ter sido ruim. Uma classificação de um ou dois é considerada ruim, três ou quatro é bom e cinco é excelente. Embora seja um pouco de um indicador à demora, essa é uma métrica útil para descobrir problemas que métricas de serviço podem perder.

> [!NOTE]
> Até que os usuários são instruídos para responder às pesquisas RMC, oferecendo uma boa indicação além das respostas mal, normalmente volte como predominantemente negativo. A maioria dos usuários responder somente quando a qualidade da chamada é ruim. Dessa forma, seus relatórios RMC podem ser enviesados até o lado ruim mesmo enquanto métricas de serviço estão funcionando bem. 


Você pode usar CQD para reportar sobre as respostas do usuário RMC e relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são abordados em detalhes neste guia. Para obter mais informações sobre o RMC Skype para Business Online e orientações para instruir os usuários a fornecer respostas RMC úteis, consulte esta [postagem de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorias de qualidade

O sucesso do operacionalização de uma implantação de alta qualidade e confiável depende da sua rigor operacionais de construção. Especificamente, prestar bastante atenção em três categorias ilustrado na figura a seguir; Estes são o foco deste guia:

-   **Rede:** Qualidade de áudio com foco na métrica PCR, o uso TCP, sub-redes com e sem fio e identificando o uso de proxies HTTP e VPN.

-   **Pontos de extremidade:** Dispositivos de áudio e a versão do cliente (Skype para negócios apenas).

-   **Gerenciamento de serviços:** Essa categoria consiste em duas seções:

    -   A primeira é responsabilidade da Microsoft para gerenciar e manter as equipes e Skype para serviços corporativos Online.

    -   Segundo são tarefas de que sua organização deve gerenciar para garantir acesso confiável ao serviço, atualizando informações de criação e manutenção de firewalls para novos endereços IP do Office 365 infrastructure for adicionada ao serviço.

![As categorias de qualilty em uma organização: serviço de gerenciamento, pontos de extremidade e a rede.](media/quality-of-experience-review-guide-image3.png)

_Figura 3 - críticas categorias para equipes e Skype para implantação Business Online_

O gráfico a seguir descreve as tarefas que você deve executar para cada categoria. Recomendamos que você execute essas tarefas uma vez por semana, no mínimo.

Na primeira vez que você executar essas tarefas levarão pouco mais do que as iterações subsequentes, pois muitas dessas categorias exigem que você valide suas configurações de implantação. Depois que você tiver obtido o estado desejado atendendo os destinos que você definiu, execução dessas tarefas ajudará você manter esse estado.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Em um mundo primeiro nuvem, você deve executar algumas tarefas de gerenciamento de serviço para manter as experiências do usuário de alta qualidade. Essas tarefas variam de garantir que não há largura de banda suficiente para alcançar o serviço sem links de internet, validando que qualidade de serviço (QoS) de saturação é no lugar em todas as áreas de rede gerenciada, e — finalmente — permanecendo na parte superior [intervalos de IP do Office 365 em firewalls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: qualidade e confiabilidade. Confiabilidade enfoca medindo a capacidade do usuário para fazer chamadas com êxito e permanecem conectadas. Qualidade enfoca a telemetria agregada enviada para equipes e Skype para Business Online pelo cliente do usuário durante e depois que ela for encerrada.

Dado o impacto crítico que confiabilidade tem sobre a experiência do usuário, começar avaliar e investigando dessas métricas antes de começar em qualidade.

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nesta categoria está validando a quais versões do cliente estiver executando o Skype para negócios em compilações da área de trabalho do últimos seis meses para garantir que os usuários estão obtendo o benefício das otimizações contínuas feitas do Skype para o cliente de desktop de negócios. Além disso, isso simplifica as tarefas de gerenciamento de cliente geral e fornece uma experiência de usuário consistente.

A área de importante é quais dispositivos estão predominantes em sua implantação de monitoramento e orientando o uso de dispositivos de certificados para oferecer a melhor experiência de usuário.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.


## <a name="using-the-reports"></a>Usando os relatórios

Esta seção descreve os conceitos básicos sobre como trabalhar com CQD. Orientação é fornecida para os seguintes tópicos:

-   Localizando sua ID de Inquilino

-   Relatórios em equipes versus Skype para negócios

-   Primeiro versus segunda classificações

-   Medidas, dimensões e filtros

-   Fluxos de versus chamadas

-   Chamadas boas, ruins e não classificadas

-   Introdução ao CQD

-   Edição de relatórios no CQD

-   Filtragem de relatórios no CQD

Para obter mais aprofundado treinamento e recursos, consulte o [Apêndice](#other-resources).

### <a name="tenant-id"></a>ID do inquilino

Alguns relatórios CQD exigem a inclusão de um filtro para sua ID de Inquilino. Devido a maneira como CQD agrega os dados de telemetria participantes federada é incluída.
Embora isso sejam valioso ao analisar as métricas de chamadas ruins, os relatórios de clientes e dispositivos exigem a filtragem de dados para um locatário específico a serem excluídas telemetria participantes federada. Se você não souber seu ID do inquilino, você pode usar um dos métodos a seguir para localizá-lo.

Requisitos de permissão

-   Função de administrador global

-   Skype para a função de administrador de negócios

#### <a name="azure-ad-portal"></a>Portal do Azure AD

1.  Logon no portal do Microsoft Azure:<https://portal.azure.com>

2.  Selecione o **Azure Active Directory**.

3.  Em **Gerenciar**, selecione **Propriedades**. A ID do inquilino é mostrada na caixa **ID do diretório** .

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Instale o módulo de gerenciamento de serviço do Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra uma janela de comando do Azure PowerShell e execute o seguinte script, inserir suas credenciais do Office 365, quando solicitado:  
    **AzureRmAccount de login**

3.  A ID do inquilino está listada na saída.

#### <a name="skype-for-business-online-admin-center"></a>Skype para negócios Online Admin Center

1.  Ir para<https://portal.office.com>

2.  Entrar com sua conta organizacional do administrador de locatário.

3.  Selecione **Skype para negócios** sob **Centros do administrador**.

4.  A ID do inquilino está listada como **ID da organização** , na página de boas-vindas.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para negócios Online usando o PowerShell

1.  [Conectar-se ao Skype para negócios Online por meio do PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Execute o seguinte comando:  
    **.Tenantid (get-cstenant)**

3.  A ID do inquilino é exibida como um GUID.

### <a name="teams-vs-skype-for-business"></a>As equipes versus Skype para negócios

CQD pode relatar equipes e Skype para telemetria de negócios. No entanto, pode haver ocasiões em que você deseja desenvolver um relatório a ser analisado telemetria de equipes separada do Skype para negócios.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios de resumo a ser analisado apenas equipes ou Skype para negócios, selecione o menu suspenso de **Filtro de produto** da parte superior da tela e selecione o produto desejado.

![Captura de tela do painel de qualidade de chamada refletindo um menu drop-down mostrando a opção de filtragem por carga de trabalho.](media/quality-of-experience-review-guide-image4.png)

_Figura 4 - Selecione um filtro de produto_

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar um relatório detalhado, adicione o filtro **É equipes** ao relatório e defini-la como True ou False. Para obter mais informações, consulte [relatórios de edição](#editing-reports) , mais adiante nesta seção.

![Captura de tela do painel de qualidade de chamada que descrevam o servidor de dados que pode ser adicionado a um relatório detalhado.](media/quality-of-experience-review-guide-image5.png)

_Figura 5 - adicionando um filtro de Teams da Microsoft a um relatório_

### <a name="dimensions-measures-and-filters"></a>Medidas, dimensões e filtros

Uma consulta CQD bem formada contém todas as três dos parâmetros a seguir:

-   **Dimensão:** Como eu desejo os dados de tabela dinâmica.

-   **Medida:** O que eu quero a ser relatado no.

-   **Filtro:** Como deseja reduzir a consulta retornar o conjunto de dados.

Outra maneira de analisar isso é uma dimensão é a função de agrupamento, uma medida é os dados que estou interessado em e um filtro é como eu quiser restringir os resultados para aqueles que são relevantes à minha consulta.

Um exemplo de uma consulta bem formado é "Mostrar-me fluxos ruins [medida] pela sub-rede [Dimension] para construção 6 [filtro]."

Para obter mais informações, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

Para filtros para os relatórios usados nos modelos de CQD, medidas e dimensões, consulte o [Apêndice](#CQD-training).

### <a name="first-vs-second"></a>Primeiro versus segundo 

Muitas das dimensões e medidas em CQD são classificadas como primeira ou segunda.
CQD não usa os campos de chamador/receptor — eles tiverem sido renomeado _primeiro_ e _segundo_ porque há etapas intermediárias entre o chamador e o receptor. A seguinte lógica determina qual ponto de extremidade envolvido no fluxo ou na chamada é rotulado como o primeiro:

-   Primeiro sempre será um ponto de extremidade do servidor (servidor de conferência, o servidor de mediação e assim por diante) se um servidor que está envolvido na chamada ou stream.

-   Em segundo lugar sempre será um ponto de extremidade do cliente, a menos que o stream está entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade são do mesmo tipo, a escolha do qual é a primeira é baseada em ordem interna da categoria de agente de usuário. Isso assegura que a ordenação seja consistente.

Para obter mais informações sobre como determinar o ponto de extremidade de primeiro ou segundo quando eles estão ambos os mesmos, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream versus chamada

Você precisa entender a diferença entre uma chamada e um stream adequadamente escolher quais dimensões ou medidas você vai ser observando em CQD.

**Stream:** Um fluxo existirá apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são exigidos para a comunicação. Fluxos são úteis para analisar os prédios ou redes. Em alguns casos, a chamada e stream são usados no nome de usuário (por exemplo, fluxo de instalação chamada ou chamada ignorados Stream).
Eles ainda são classificados como único fluxos.

**Chamar:** Uma chamada é um agrupamento de todos os fluxos de todos os participantes. Consiste em uma chamada — no mínimo — dois fluxos. Uma única chamada terá dois participantes cada com um mínimo de um stream. As chamadas são úteis para análise de tendências ao longo do tempo.

Para obter orientação adicional sobre a dimensão ou medida fizer referência a uma chamada ou um stream, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada por como BOM, baixa ou não classificados. Vamos falar sobre cada uma em mais detalhes um pouco.

**BOM ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado.
Determinar se uma chamada é bom ou ruim está descrito [neste guia](#pcr).

**Não classificados:** Uma chamada não classificada não contém um conjunto completo de métricas de serviço. Essas são frequentemente chamadas curtas — geralmente menor que 60 segundos — onde não puderam ser computadas médias e um relatório de QoE não foi gerado.

### <a name="access-cqd-online"></a>Acesso CQD Online

Você pode acessar CQD de duas maneiras.

-   Vá para <https://cqd.lync.com>.

-   Vá para **Skype para centro de administração de negócios** \> **Ferramentas**e selecione o link para CQD, conforme mostrado abaixo.

![Captura de tela mostrando "ferramentas" selecionadas no painel de navegação esquerdo e o link para "Skype para Business Online chamada qualidade Dashboard" selecionada.](media/quality-of-experience-review-guide-image6.png)

_Figura 6 – acessando CQD por meio do Skype para centro de administração de negócios_

### <a name="getting-started"></a>Introdução

Quando você procurar primeiro CQD, você verá a página relatórios de resumo. A maioria dos relatórios descritos neste guia são relatórios detalhados personalizados. Para começar a usar os relatórios detalhados, selecione **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

![Captura de tela de depcting o painel de controle de qualidade de chamada os diferentes tipos de relatórios que estão disponíveis.](media/quality-of-experience-review-guide-image7.png)

_Figura 7 - navegando para relatórios detalhados_

A página de relatórios detalhados no CQD se parece com a figura mostrada abaixo.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório.](media/quality-of-experience-review-guide-image8.png)

_Figura 8 - página de relatórios detalhados_

1.  O painel Resumo mostra contexto para o conjunto de relatório que aparece à direita.

2.  Você pode selecionar **Editar** no painel Resumo para definir propriedades de nível de relatório – (incluindo a altura do eixo y).

3.  Navegação estrutural ajuda os usuários a identificar sua localização atual na hierarquia do conjunto de relatório.

4.  Relatórios que têm filhos relatórios são mostrados com um link azul. Selecionando o link, você pode analisar os relatórios de filho.

Aponte para os gráficos de barras e as linhas de tendência para exibir valores detalhados. O relatório que tem o foco mostrará no menu Ação: **Editar**, **Clone**, **Excluir**, **Baixar**e **Exportar árvore de relatório**.

### <a name="editing-reports"></a>Edição de relatórios

Quando você seleciona **Editar** no menu Ação, de um relatório, você vai abrir o Editor de consulta. Cada relatório é feito por uma consulta. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de consulta é uma interface do usuário para edição essas consultas além das opções de exibição para o relatório, como ilustrado na figura a seguir.

![Captura de tela da página relatório detalhado no CQD e os diferentes elementos que compõem um relatório quando o relatório está sendo editado.](media/quality-of-experience-review-guide-image9.png)

_Figura 9 - Editor de relatório_

1.  Você escolher medidas, dimensões e filtros de painel à esquerda. Apontando para um valor existente exibe um botão Fechar (**X**) que você pode optar por remover o valor.

    1.  Selecionando a dimensão ou medida, você pode alterar o título editando o campo **cargo** . Você também pode alterar a ordem selecionando o azul aumentar ou diminuir setas no painel superior.

    2.  Selecionando (**+**) ao lado de um título abre a caixa de diálogo para adicionar uma nova dimensão, uma medida ou um filtro.

    3.  Digite as primeiras letras da dimensão, medida ou filtro no **encontrar um** campo para filtrar a lista para facilitar a pesquisa.

2.  O painel superior mostra as opções de personalização do gráfico.

3.  O Editor de consulta mostra uma visualização do relatório.

4.  Use a caixa **Editar** na parte inferior da tela para criar ou editar uma descrição detalhada do relatório.

### <a name="filtering-reports"></a>Filtragem de relatórios

Os modelos fornecidos inclui várias consultas integradas e filtros do relatório. As seções a seguir descrevem os filtros mais comuns usados em todo os modelos.

#### <a name="cqd-filter"></a>Filtro CQD

Você pode usar o filtro CQD ou o filtro de URL, filtrar temporariamente cada consulta de relatório. O filtro de CQD mais comuns que você utilizará é filtrar relatórios a serem excluídas telemetria participantes federada. Recomendamos que você crie um indicador esse filtro para que ele se torna o modo de exibição padrão. Excluindo dados federados de relatórios CQD é útil quando você estiver correção prédios gerenciados ou redes onde os dados federados podem influenciar seu relatório.

Para implementar um filtro CQD, na barra de endereço do navegador, acrescente o seguinte ao final da URL:

/Filter/ [AllStreams]. [Id do inquilino segundo] \|[Sua ID do INQUILINO aqui]

**Exemplo:**  
https://cqd.lync.com/cqd/\#/1234567/2018-02/filter/[AllStreams]. [Id do inquilino segundo] \|[TENANTID] & locatário = TENANTID

> [!NOTE]
> O exemplo de URL acima destina-se somente a representação visual. Use o link CQD padrão de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta são implementados usando o Editor de relatório. Esses filtros são usados para reduzir o número de registros retornados por CQD, minimizando o tamanho de geral do relatório. Isso é especialmente útil para filtragem de redes não gerenciados.
Os filtros abaixo usam expressões regulares (RegEx).

_Tabela 3 - filtros de consulta_

| Filtro               | Descrição          | Exemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores em branco         | Alguns filtros não tem a opção para filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e definir o filtro é igual a ou não for igual a, dependendo das suas necessidades.                                                                                                                             | Construção do segundo nome \< \> \^ \\s\*\$                       |
| Populares sub-redes residencial | Sem um arquivo de construção válido para separar gerenciada de redes não gerenciados, redes domésticas terão obter incluídos nos relatórios. Essas sub-redes residencial estão fora do escopo do controle de TI e podem ser rapidamente excluídos de um relatório. Populares sub-redes residencial, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Inside versus fora   | Usado para filtrar um relatório para (interna) gerenciado ou (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.                                                                                                                                                                                | Segundo dentro Corp = dentro                               |

#### <a name="report-filters"></a>Filtros do relatório

Filtros do relatório são implementados adicionando um filtro ao relatório renderizado tanto no relatório Editor ou diretamente ao relatório. Os filtros de relatórios a seguir são usados em todo o modelo.

_Tabela 4 - filtro de relatório_

| Filtro     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Comece com o ano primeiro e, em seguida, mês. | 10 de 2017                           |
| Alfabético | Filtra quaisquer caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos os caracteres numéricos.    | [0-9]                             |
| Porcentagem | Filtra uma porcentagem.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar os modelos CQD

Este guia inclui [dois modelos CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Esses modelos aceleram seu uso de CQD e fornecem a você uma oportunidade para aproveitar rapidamente os recursos do CQD para tornar um impacto sobre equipes ou do Skype dos usuários para a experiência de negócios. O modelo de todas as redes, porém otimizado para funcionar com um edifício pode ser usado o arquivo de dados, enquanto você trabalha em direção a coleta e carregamento de informações de construção em CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) em CQD Online**

1.  Vá para <https://cqd.lync.com>.

2.  Autentica usando suas credenciais administrativas do Office 365.

> [!NOTE]
> Você deve ter o Office 365 Global administrador Skype para administrador de negócios ou função de leitores de relatório acessar CQD. 


3.  Selecione o menu de **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

4.  No painel Resumo, selecione **Importar**. Vá para o CQDX salvo local, selecione o modelo CQDX e selecione **Abrir**.

5.  Depois que o modelo for carregado, uma janela pop-up será exibida a mensagem "a importação de relatório teve êxito." Selecione **Okey.**

![Captura de tela de uma janela pop-up que notifica o usuário se o modelo foi importado com êxito.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita as etapas 4 e 5 para o segundo modelo CQD.

> [!NOTE]
> Os modelos CQD são importados por usuário. Se outros usuários precisarem usar o relatório, eles devem entrar e importar os modelos em sua instância CQD. 


## <a name="building-mapping"></a>Mapeamento de construção

Em um equipes ou Skype para implantação Business Online, todos os clientes são externos.
Que tem a implicação que, por padrão, todos os clientes são indicados como fora em CQD Online, independentemente de se o cliente foi conectado em uma rede corporativa interna.

Quando você trabalha com a qualidade de chamada, você precisa saber o local de um cliente e se ele foi conectado a uma rede que você pode gerenciar ou de uma rede não é possível gerenciar — a pressuposição sendo que você só pode melhorar redes você pode gerenciar.
Carregando informações de construção e rede para CQD Online, você deve habilitar CQD determinar se um cliente foi conectado a uma rede interna de corporativo/gerenciados ou a uma rede externa/não gerenciados.

### <a name="building-data-file-structure"></a>Estrutura do arquivo de dados de construção

O formato do arquivo de dados que você carrega deve atender aos seguintes requisitos para passar a verificação de validação antes de carregar.

-   O arquivo deve ser um arquivo TSV, o que significa que, para cada linha, cada coluna é separada por um caractere de tabulação, ou um arquivo CSV no qual cada coluna é separada por uma vírgula.

-   O arquivo não pode ser maior do que 50 MB.

-   O conteúdo dos dados de arquivo *não deve incluir cabeçalhos de tabela*. Em outras palavras, a primeira linha do arquivo de dados deve ser dados reais, e não os títulos de coluna, como "Rede".

-   Para cada coluna, o tipo de dados só pode ser cadeia de caracteres, número ou Bool. Se o tipo de dados for um número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.

-   Para cada coluna, se o tipo de dados é a cadeia de caracteres, os dados podem estar vazios (mas ainda devem ser separados por um delimitador apropriado, que é um caractere de tabulação ou por vírgula). Isso simplesmente atribui esse campo um valor de cadeia de caracteres vazia.

-   Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados descrito na tabela a seguir, e as colunas devem estar na ordem listada na tabela.

_Tabela 5 - Criando a estrutura do arquivo_

| Nome da coluna        | Tipo de dados | Exemplo                   | Orientação    |
|--------------------|-----------|---------------------------|-------------|
| Rede            | Cadeia de caracteres    | 192.168.1.0               | Obrigatório    |
| NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-mar-1 | Necessário\*  |
| NetworkRange       | Número    | 26                        | Obrigatório    |
| BuildingName       | Cadeia de caracteres    | SEATTLE-MAR-1             | Necessário\*  |
| OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional    |
| BuildingType       | Cadeia de caracteres    | Terminação de IT            | Opcional    |
| BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional    |
| Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado |
| CEP            | Cadeia de caracteres    | 98001                     | Recomendado |
| País            | Cadeia de caracteres    | CONOSCO                        | Recomendado |
| Estado              | Cadeia de caracteres    | WA                        | Recomendado |
| Região             | Cadeia de caracteres    | MSUS                      | Recomendado |
| InsideCorp         | Bool      | 1                         | Obrigatório    |
| ExpressRoute       | Bool      | 0                         | Obrigatório    |

\*Embora não seja necessário por CQD, os modelos estão configurados para exibir a criação e a rede nome.

#### <a name="supernetting"></a>Combinação de redes

Você pode usar a combinação de redes, geralmente chamado de roteamento entre domínios sem classificação (CIDR), no lugar de definição de cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR. Combinação de redes é suportada, mas não recomendamos utilizá-lo.

Por exemplo, a construção de marketing da Contoso é composta das sub-redes abaixo:

-   10.1.0.0/24 – primeiro andar

-   10.1.1.0/24 – 2º andar

-   10.1.2.0/24 – 3º andar

-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted/CIDR — neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0

-   Intervalo de rede = 22

Aqui estão algumas coisas a considerar antes de implementar a combinação de redes:

-   Combinação de redes demora menos tempo desde o início, mas que se refere ao custo reduzir o aperfeiçoamento em termos de seus dados. Digamos que não há uma sub-rede de envolvendo do problema de qualidade 200.1.2.0. Se você implementou a combinação de redes, você não saberá onde a sub-rede está localizada no edifício ou tipo de rede que está (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes de um edifício e carregado informações de local andar, você poderá ver essa distinção.

-   É importante garantir que o endereço de supernetted/CIDR está correto e se não está capturando sub-redes indesejadas.

-   Combinação de redes pode ser usada em um mapeamento de construção com máscara de 8 bits para 28 bits.

-   Ele é bastante comum para encontrar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outras pessoas, esse é o esquema de endereço IP de um escritório de satélite. Se sua organização tem escritórios que usam essa configuração, não incluí-lo em seu arquivo de construção conforme é difícil distinguir entre redes domésticas e internos usando sub-redes comuns.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todas as novas criar carregamentos de arquivos de dados será verificado para todos os intervalos de sobreposição. Se você carregou anteriormente um arquivo de construção, você deve baixar o arquivo atual e carregá-la novamente para identificar qualquer sobreposições e corrigir o problema. Qualquer sobreposição nos arquivos carregados anteriormente pode resultar em mapeamentos de sub-redes aos prédios nos relatórios errados. 


#### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Office 365 — que é onde os dados CQD originados de — inclui um sinalizador VPN. No entanto, esse sinalizador depende de relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN registrado é um adaptador de acesso remoto. Nem todos os fornecedores VPN adequadamente registre os adaptadores de acesso remoto. Dessa forma, você não poderá usar os filtros de consulta VPN internos. Há duas abordagens para acomodar sub-redes VPN no edifício arquivo de informações.

-   Defina um **Nome de rede** usando o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma sub-rede VPN](media/quality-of-experience-review-guide-image10.png)

_Figura 10 - VPN usando o nome de rede_

-   Defina um **Nome de construção** usando-se o texto "VPN" neste campo para sub-redes da VPN.

![Captura de tela de um relatório no painel de qualidade de chamada que define como criar uma definição de construção que consiste em uma sub-rede VPN.](media/quality-of-experience-review-guide-image11.png)

_Figura 11 - VPN usando o nome do edifício_

> [!IMPORTANT]
> Determinadas implementações de VPN com precisão não relatam informações de sub-rede. Se isso ocorrer em seu relatório, que é recomendável que, quando você adiciona uma sub-rede VPN para o arquivo de construção, em vez de uma entrada para a sub-rede, adicione entradas separadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você tem 253 linhas, com uma linha para cada endereço de 172.16.18.1/32 por meio de 172.16.18.254/32, inclusive.


> [!NOTE]
> Conexões VPN são conhecidas por cometem erros conforme com fio quando a conexão de internet subjacente está na identificação de conexão de rede sem fio. Ao olhar qualidade em conexões VPN, você não pode assumir que o tipo de conexão foi identificado com precisão.

### <a name="uploading-building-information"></a>Carregar informações de construção

O painel de relatórios de resumo de CQD inclui uma página de **Carregamento de dados de Inquilino** , acessada selecionando a marca de link de **Carregamento de dados de Inquilino** no canto superior direito (procure o ícone de engrenagem). Esta página é usada para os administradores para carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeando cada ponto de acesso sem fio e seu endereço MAC e assim por diante.

1.  Vá para CQD Online navegando até <https://cqd.lync.com>.

2.  Selecione o ícone de engrenagem no canto superior direito e escolha o **Carregamento de dados de Inquilino** na página **Relatórios de resumo** .

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que é exibido enquanto dados está sendo carregados.](media/quality-of-experience-review-guide-image12.png)

_Figura 12 - menu de carregamento de dados de Inquilino_

1.  Como alternativa, se essa for a primeira vez em que visitando CQD, você será solicitado para carregar dados de construção. Você pode selecionar **Carregar Agora** para navegar rapidamente para a página de **Carregamento de dados de Inquilino** .

![Captura de tela de um banner no painel de qualidade de chamada que notifica o usuário para carregar dados de construção.](media/quality-of-experience-review-guide-image13.png)

_Figura 13 - Criando banner de carregamento de dados_

1.  Na página de **Carregamento de dados de Inquilino** , selecione **Procurar** para escolher um arquivo de dados.

2.  Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, especifique uma data de término.

3.  Depois de selecionar a **Data de início**, selecione **carregar** para carregar o arquivo para o CQD. <br><br>Antes do arquivo for carregado, ele será validado. Se a validação falhar, uma mensagem de erro é exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.

![Captura de tela de uma caixa de diálogo no painel de qualidade de chamada que descreve uma mensagem de erro ao importar dados de construção.](media/quality-of-experience-review-guide-image14.png)

_Figura 14: Criando o erro de carregamento de dados_

4.  Se nenhum erro ocorrer durante a validação, o carregamento de arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregados na **Minhas carregamentos de** tabela, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já tiver carregado um arquivo de construção e precisa para adicionar as sub-redes que podem ter sido perdidas ou excluídos, modifique o arquivo original adicionando novas sub-redes, remova o arquivo atual e reenvie o arquivo recentemente editado. Pode haver construção ativa apenas um arquivo de dados em CQD. 

### <a name="missing-subnets"></a>Sub-redes ausentes

Após carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre é o caso; Normalmente, as sub-redes alguns são perdidas. Esta seção aborda como validar as redes ausentes.

Navegue até a página de **Relatórios detalhados** no CQD Online e navegue até o **Relatório de sub-rede ausentes** incluídas nos modelos CQD. Isso apresenta todas as sub-redes com 10 ou mais áudio fluxos que não são definidos no edifício arquivo de dados. Certifique-se de que não há nenhuma redes gerenciadas nessa lista. Se não existirem sub-redes, atualize o edifício original do arquivo de dados e reenvie a CQD.

> [!IMPORTANT]
> Você precisará adicionar sua ID de Inquilino como um filtro de consulta para a **Segunda ID do inquilino** para este relatório para filtrar o relatório para exibir somente os dados de inquilinos da sua organização. Caso contrário, o relatório mostrará sub-redes federados.

> [!NOTE] 
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.                                                  |

![Relatório mostrando as sub-redes não são incluídos no arquivo de dados de construção CQD que mostram o uso.](media/quality-of-experience-review-guide-image15.png)

_Figura 15 - ausente relatório de construção_

## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para aprimorar a qualidade é para avaliar o estado de confiabilidade de áudio em toda a organização. Confiabilidade de áudio, pois é vital para uma experiência de usuário positivo iniciamos com os dois componentes que medem confiabilidade:

1.  **Falhas de instalação de chamada:** Sessão não pôde ser estabelecida.

2.  **Falhas de recebimento de chamadas:** Sessão foi estabelecida e finalizada inesperadamente

Ao longo desta seção, abordaremos métodos para ambas as áreas de investigar.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações.


### <a name="call-setup"></a>Configuração da chamada

Priorize remediando falhas de instalação chamada nessa área em primeiro lugar, pois essas falhas possuem um impacto negativo significativo na experiência do usuário.

Começar a investigação avaliando a porcentagem de falhas de instalação chamada geral para a organização e, em seguida, priorizar áreas de investigação com base na porcentagem mais alta, criação ou da rede.

#### <a name="call-setup-failures-overall"></a>Falhas de instalação gerais de chamadas

Este relatório de gráfico exibe a quantidade total de chamada bem sucedida, configurar e falhas de instalação de chamadas ao longo do tempo. Aponte para qualquer uma das colunas para exibir seus valores individuais, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico que mostra o percentual de falha na instalação do fluxo de chamadas de áudio](media/quality-of-experience-review-guide-image16.png)

_Figura 16 - confiabilidade de áudio - falhas de instalação de fluxo de chamada_

##### <a name="analysis"></a>Análise

Este relatório exibe o uso da instalação chamada de áudio e falhas de sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas e determinar sua próxima ação:

1.  Qual é a porcentagem de falha de instalação chamada total para o mês atual?

2.  É a porcentagem de falha de instalação chamada total abaixo ou acima a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório informará a história da frequência suas configurações gerais de chamada estão falhando em toda a organização.

Independentemente das respostas anteriores, reserve um tempo para investigar maior usando os sub-relatórios incluídos para procurar por qualquer prédios individuais ou redes que possam precisar de remediação. Embora a taxa de falha geral pode estar abaixo na métrica de destino, geralmente as taxas de falha para uma ou mais redes ou prédios são acima na métrica e precisam remediação.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Falhas de instalação de chamada Construindo e sub-rede 

Este relatório de tabela é usado para descobrir e isolar qualquer prédios ou redes que precisam de correção.

> [!NOTE]
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.


![Relate que razões de falha de instalação de chamada de listas, organizados construindo, a rede e a sub-rede por mês.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - falhas de configuração de áudio, criando ou sub-rede_

##### <a name="remediation"></a>Remediação 

Concentre os esforços de remediação em prédios ou sub-redes que tenham o maior volume de falhas em primeiro lugar, porque isso maximizar o impacto sobre a experiência do usuário e ajudam a reduzir rapidamente as falhas de instalação chamada organizacionais.
A tabela a seguir lista as duas razões para falhas de instalação chamada conforme relatado pelo CQD.

_Tabela 6 – razões para falhas de instalação chamada_

| Chamar o motivo de falhas de instalação                       | Causa comum                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Regra de isenção de inspeção de pacotes de profundidade de firmware de ausentes | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida devido às regras de inspeção de pacotes de profundidade. Isso é provável devido às regras de firewall não está sendo configuradas corretamente. Neste caso o handshake TCP foi bem-sucedida, mas o handshake SSL não especificou.               |
| Regra de exceção do bloco de IP de firmware de ausentes               | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida com a rede do Office 365. Isso pode ser devido às regras de firewall ou proxy não está sendo configuradas corretamente para permitir acesso aos endereços IP e portas usadas para equipes e Skype para tráfego de negócios. |

Agora como começar sua remediação, é possível focar seus esforços em um edifício ou sub-rede. Conforme mostra a tabela anterior, esses problemas são devido às configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de remediação.

_Tabela 7 - próximas etapas para a chamada de correção de falha de instalação_

| Remediação           | Orientação     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewalls | Trabalhar com a equipe de rede e verifique se a sua configuração de firewalls contra [a lista de endereços IP do Office 365](https://aka.ms/o365ips). Verifique se as portas e [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) são incluídas nas regras de firewall. Verifique se que as portas TCP e UDP necessárias sejam abertas no firewall. Mídia prefere UDP sobre TCP. TCP é considerado um protocolo de failback.<br><ul><li>**TCP:** a porta 443</li><li>**UDP:** portas 3478 – 3481</li><ul> |
| Verifique se                | Utilize a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar a conectividade do edifício afetado ou sub-rede usando a função de verificação de conectividade.    |


### <a name="call-drop"></a>Recebimento de chamadas

Ao contrário de falhas de instalação chamada, não há nenhum código de motivo para indicar por que a chamada abandonada falhas ocorreu, o que torna difícil isolar uma causa raiz específica. Para melhor triagem chamadas capitular, use uma abordagem deduzida. Correção de quaisquer áreas de interesse para áudio, os clientes de aplicação de patch e orientando o uso de dispositivos de certificados para equipes e Skype for Business, você esperaria falhas de chamada queda para recusar.

#### <a name="call-drop-failures-overall"></a>Geral de falhas de recebimento de chamadas

Este relatório de gráfico exibe a quantidade total de fluxos de áudio, fluxos de áudio total ignorados, e a porcentagem de queda de fluxo total. Aponte para qualquer uma das colunas para exibir seus valores, conforme mostrado na figura a seguir.

![Captura de tela de um gráfico mostrando a porcentagem de queda de fluxos de áudio de chamada](media/quality-of-experience-review-guide-image18.png)

_Figura 18 - chamada Total queda percentual de falha_

##### <a name="analysis"></a>Análise

Este relatório de gráfico exibe a falhas e o uso da sua organização ao longo do tempo relacionado ao chamar quedas. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a chamada atual de total queda porcentagem?

2.  É a porcentagem do total de depósito abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

As informações apresentadas neste relatório podem saber a história da frequência suas geral quedas de chamada estão ocorrendo em toda a organização.

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. Embora a taxa geral de recebimento pode estar abaixo na métrica de destino, muitas vezes a taxa de recebimento de um ou mais redes ou prédios estiver acima na métrica e precisa remediação.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Falhas de recebimento de chamadas pela criação ou sub-rede

Falhas neste relatório de tabela indicam que a chamada foi interrompida inesperadamente e resultou em uma experiência de usuário negativo. Existem dois relatórios de tabela incluídos no modelo, um para investigar a conferência e outro para duas partes.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.


![Relatório que relaciona o número e a porcentagem de queda de chamadas, organizadas por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image19.png)

_Figura 19 – a chamada de áudio queda de falhas pela criação ou sub-rede_

##### <a name="remediation"></a>Remediação

Usando o relatório de tabela anterior, você pode isolar agora "pontos de acesso" na rede gerenciada onde quedas de chamada ocorrerem acima a métrica destino definida. Concentre os esforços de remediação em prédios ou redes que possuem a contagem de fluxo total mais alta primeiro, para tornar o maior impacto.

Causas comuns de quedas de chamada:

-   Saída de rede ou internet em provisionado

-   Nenhum QoS configurado em redes restritas

-   Versões mais antigas do cliente

-   Comportamento do usuário

Depois que você descobrir os pontos de acesso, você pode aproveitar a [Chamada análise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar ainda mais usuários em que construção para problemas específicos. Análise de chamada contém dados PII e pode ser útil para isolar ainda mais os motivos possíveis para a cai de chamada.

Independentemente da sua próxima etapa, é uma boa prática para notificar a helpdesk que foi descoberto um problema com os prédios específicos ou sub-redes. Dessa forma, rapidamente eles podem responder às chamadas recebidas e triagem usuários com mais eficiência. Usuários sinalizados, em seguida, podem ser informados volta para a equipe de engenharia para uma investigação detalhada.

A tabela a seguir lista alguns métodos comuns para gerenciar e remediar quedas de chamada.

_A tabela 9 - próximas etapas para chamada drop remediação_

| Remediação                              | Orientação     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rede/internet                         | Agora que você sabe qual construção é afetada, trabalhe com a equipe de rede para monitorar a largura de banda em que construção para determinar se há problemas com excesso. Se o problema for detectado estar relacionado ao congestionamento da rede, considere o aumento de largura de banda para essa construção. <br><br>**QoS:** Se o aumento da largura de banda é impossível ou caro, considere a implementação de QoS. Isso garantirá a pacotes de mídia na rede gerenciada são priorizados acima tráfego de mídia não. Como alternativa, se não houver nenhuma evidência clara que largura de banda é o responsável, considere estas soluções:<br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação. <br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra os [requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clientes (Skype para negócios apenas Online) | Alguns clientes mais antigos possuem conhecidos, documentados problemas com confiabilidade de mídia. Revise os relatórios de análise de chamada de vários usuários afetados ou crie um relatório de tabela de versão do cliente personalizado no CQD filtrado específicos prédios ou sub-redes com medida de % do Total de chamadas queda de falha. Essas informações ajudarão você a entender se existe uma relação entre quedas de chamada na que edifício específico e uma versão específica do cliente.                                                                                                                                                              |
| Dispositivos                                  | A maioria das falhas de dispositivo são devido ao uso de dispositivos que não são certificados para equipes ou Skype para negócios. Falhas normalmente assumem a forma do integrada de alto-falantes ou microfones que estão sendo usados ou combinações de earbud/microfone estão conectadas à tomada de áudio de 3,5 mm em um dispositivo. Recomendação de atual da Microsoft é que todos os usuários que estão enfrentando chamar quedas — ou ruins chama em geral — e estão usar dispositivos integrados ou drivers deve ser provisionado um [certificado headset ou viva-voz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamento do usuário                            | Se achar que nem rede, dispositivos ou clientes são o problema, considere o envolvimento do [Meu Advisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de adoção de usuário para instruir os usuários como práticas ingressar e sair de reuniões. As equipes de uma forma mais inteligente e Skype usuário produzirá uma melhor experiência de usuário para todos os participantes da reunião. Um usuário que coloca seus laptops em suspensão (fechando a tampa) sem sair da reunião será classificado como um depósito chamada inesperada.     |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade de áudio entre a implantação é investigar áudio ruim chamada proporção (PCR), TCP e uso de proxy. É importante lembrar que os dados CQD não fornecem uma causa raiz específica, mas fornece em vez disso, com áreas de problema provavelmente iniciar uma conversa de colaboração com as equipes apropriadas para atividades de correção.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="investigate-call-quality"></a>Investigar a qualidade da chamada

A porcentagem PCR geral é usada principalmente para indicar se a organização é reunião destinos de métricas de áudio definidos. É importante observar que, mesmo se a porcentagem geral estiver dentro de destino, alguns sub-redes ou prédios talvez não cumprir os objetivos definidos e, portanto, precisa as investigações. Por exemplo, se a porcentagem PCR áudio organizacional for % 3 em dezembro, que atende o destino de amostra, prédios específicos pode ainda ser tendo experiências ruins, dependendo da distribuição de que % 3.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentagem de chamadas ruins organizacional geral

Para avaliar a porcentagem geral de chamadas de baixa para a organização usar o relatório de gráfico de qualidade geral.

![Captura de tela de um gráfico mostrando a porcentagem de chamadas de baixa qualidade](media/quality-of-experience-review-guide-image20.png)

_Figura 20 – qualidade de áudio - geral_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe PCR e o uso da sua organização ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É a tendência de falha pior ou melhor do que o mês anterior?

4.  É a tendência de falha aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que podem precisar de mais investigação. Embora a PCR geral pode estar abaixo na métrica de destino, muitas vezes PCR para um ou mais prédios ou redes estiver acima na métrica e precisa ainda mais investigação.

#### <a name="audio-quality-overall"></a>Qualidade de áudio geral

Há duas árvores de relatório incluídas nos modelos de qualidade de áudio, um para investigar a conferência e outro para chamadas de duas partes. Para fins de remediação de qualidade, o processo de investigação é a mesma, portanto focaremos aqui na conferência. Melhorias na qualidade de conferência também positiva afetará a qualidade das chamadas de duas partes. Relatórios também são incluídos para exibir a qualidade de áudio para conferências e duas partes por com fio e Wi-Fi.

> [!NOTE]
> Investigar chamadas de baixa de duas partes é semelhante ao investigando chamadas em conferência. A tarefa é identificar prédios ou sub-redes que tenham a qualidade inferior para validar se houver um padrão de chamadas ruins com outra construção ou sub-rede. 

![Captura de tela da qualidade de áudio - relatório de conferência no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image21.png)

_Figura 21 – qualidade de áudio - conferência_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe a conferência da sua organização ou uso de dois participantes e PCR ao longo do tempo. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é a PCR total para o mês atual?

2.  É a PCR abaixo a métrica destino definida?

3.  É PCR pior ou melhor do que o mês anterior?

4.  É a tendência PCR aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que talvez seja necessário investigação. Embora a PCR geral pode estar abaixo na métrica de destino, geralmente PCR para um ou mais prédios ou redes estiver acima na métrica e precisa remediação.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Fluxo de áudio ruim Construindo e sub-rede

Este relatório de tabela oferece compreensão adicional sobre o que contribuíram para as chamadas sendo classificada como pobre e ajuda a isolar os pontos de acesso da rede gerenciada.

Os detalhes de conexão distingue com fio e Wi-Fi e inclui as medições de tempo de ida e volta (tempo de resposta), perda de pacote e Tremulação. Um relatório semelhante também existe sob os relatórios de duas partes e é usado para isolar as chamadas de duas partes em sua rede gerenciada.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão. 

> [!TIP]
> Redes domésticas comuns são difíceis de triagem devido ao seu uso amplo. Foi adicionado um relatório separado que usa o IP do firewall para o modelo de todas as redes para auxiliar com escritórios remediando que usam redes comuns.

![Relatório que lista os tipos de conexão, tipos de transporte e PCR maior que 3%, juntamente com várias finalidades de baixa qualidade organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image22.png)

_Figura 22 - resumo de fluxo de áudio ruim, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Concentrar os esforços de remediação em prédios ou redes que possuem o maior volume de fluxos de áudio, pois isso maximizar o impacto e ajudar a melhorar o usuário experimentam rapidamente. Use a tremulação, perda de pacotes e medidas de tempo de resposta para compreender o que está contribuindo para a qualidade da chamada ruim. É possível para ter mais de um problema:

-   **Tremulação:** Pacotes de mídia chegam ao velocidades diferentes, o que faz com que um alto-falante som robótica.

-   **Perda de pacotes:** Pacotes de mídia estão sendo eliminados, que cria o efeito das palavras ou sílabas faltando.

-   **Tempo de resposta:** Pacotes de mídia estão demorando muito tempo para chegar ao seu destino, que cria um efeito de walkie-talkie.

Embora nenhuma fonte única de veracidade contas para o que pode causar uma chamada de baixa, vários métodos comuns podem ajudá-lo a lidar com problemas de rede.

Para auxiliar sua investigação sobre problemas de qualidade, você pode aproveitar a [Análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Com a análise de chamada, você pode examinar uma conferência específica ou relatório de chamada detalhada dos usuários. Este relatório conterá os dados PII e é útil quando tentar distinguir um motivo para falhas. Quando você souber qual edifício é afetado, rastreamento de usuários em que a construção deve ser simples.

Não se esqueça de informar a helpdesk que essas redes estão enfrentando problemas de qualidade, para que possam rapidamente triagem e responder às chamadas recebidas.

_A tabela 9 - comuns Contribuidores PCR alta_

| Remediação                              | Orientação       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Uma rede com uso excessivo ou em provisionado pode causar problemas com a qualidade de mídia. Trabalho com a equipe de rede para determinar se as conexões de rede do usuário até a saída de internet apontam tem largura de banda suficiente para oferecer suporte a mídia. **Executar uma avaliação de prontidão de rede:** Uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação.<br><ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. Essa ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra as de desempenho do Microsoft [requisitos](https://aka.ms/performancerequirements).<br><ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Qualidade de serviço (QoS)                 | QoS é um método comprovado para ajudar a priorizar pacotes em uma rede para garantir que eles cheguem a seu destino intacto e no tempo. Considere a implementação de QoS em toda a organização para maximizar a qualidade da experiência do usuário onde a largura de banda é limitada ou restrita. QoS ajudarão a solucionar problemas normalmente associados a altos níveis de perda de pacotes, e — a um grau menor — tempos de tremulação e de ida e volta. <br><ul><li>[Orientação de QoS equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi pode ter um impacto significativo sobre a qualidade da chamada. Design de Wi-Fi não terá normalmente em consideração os requisitos de rede para serviços de VoIP e, geralmente, é uma fonte de baixa qualidade. **QoS:** Redes sem fio modernos devem oferecer suporte a vários dispositivos. Esses dispositivos competem por largura de banda e podem causar problemas de qualidade para serviços de VoIP onde estão vitais velocidade e a latência. Consulte seu fornecedor de sem fio para obter informações específicas e considere a implementação de QoS em sua rede sem fio priorizar Skype para negócios e equipes de mídia. **Densidade AP:** Pontos de acesso (pontos de acesso) podem ser muito distantes ou não em um local ideal. Para minimizar a interferência potencial, coloque extras pontos de acesso em salas de conferência e em locais que não são obstruídos por paredes ou outros objetos. **2,4 GHz versus 5 GHz:** 5 GHz fornece menos interferência de plano de fundo e as velocidades maiores e devem ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não entrar na paredes tão facilmente. Examine seu layout de construção para determinar qual frequência você pode depender para a conexão recomendada. **Intensidade do sinal:** Em geral, medido em dBm (taxa de alimentação em decibéis), mede a intensidade do sinal sem fio. Depois que um dispositivo está conectado a um ponto de acesso, ele não quer permitir que vá facilmente. Como o dispositivo se move para fora do ponto de acesso, a intensidade do sinal cai para um ponto que induz uma conexão ruim, mesmo que a outra, quanto mais perto AP está disponível. Se possível, trabalhe com seu fornecedor de AP para garantir que os pontos de acesso estão configurados para descartar um dispositivo quando a intensidade do sinal fica abaixo de um nível aceitável. Isso garantirá que o dispositivo não congele um PA fraca. Isso é uma boa solução quando você não pode adicionar facilmente mais pontos de acesso. **Driver wireless:** Quando tudo mais falhar, certifique-se de que os drivers sem fio estão atualizados. Isso ajudará a atenuar qualquer experiência de usuário ruim relacionada a um driver desatualizado. |
| Dispositivo de rede                           | Organizações maiores podem ter centenas de dispositivos afastadas através da rede. Trabalho com a sua equipe de rede para garantir que os dispositivos de rede do usuário para a internet são mantidos e atualizados.     |
| VPN                                      | Ele foi bem documentado que aparelhos VPN tradicionalmente não são projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferido para áudio) e contam com apenas TCP. Considere a implementação de uma [solução de divisão de túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ajudar a reduzir a VPN como uma fonte de baixa qualidade.        |
| Clientes (Skype para negócios apenas Online) | Clientes mais antigos são conhecidos por causar problemas com a mídia. Certifique-se de que os clientes estão sendo patch dentro de seis meses após o lançamento. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de cliente e deploy [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | O uso de [dispositivos de otimizado](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pode ajudar a melhorar significativamente a experiência do usuário. Com todas as coisas sendo igual, dispositivos otimizados foram projetados para maximizar a experiência do usuário com equipes e Skype para negócios e produzir qualidade superior. Aproveite [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar sessões de áudio de TCP

TCP é considerado um transporte failback e não o transporte principal que você deseja para a mídia em tempo real. Isso é um transporte failback é devido à natureza do TCP com informações de estado. Por exemplo, se uma chamada for feita em uma rede latente e pacotes de mídia estão atrasados, em seguida, os pacotes de alguns segundos atrás — que não são mais úteis — competem por largura de banda chegar ao destinatário, que pode tornar um pior situação ruim. Isso torna o stitch de correção de áudio e áudio Alongar, resultando em artefatos audíveis geralmente na forma de tremulação.

Os relatórios nesta seção não fizer uma distinção entre chamadas boas e ruins. Visto que UDP é o preferido, os relatórios procuram o uso de TCP para áudio. Isso é principalmente causado pelas regras de firewall incompleta. Para obter mais informações sobre regras de firewall para equipes e Skype para Business Online, consulte [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Fluxos de áudio com o uso TCP geral

Este relatório indica o uso geral de TCP para áudio nos últimos sete meses, conforme mostrado abaixo.

Todos os relatórios mais nesta seção abordará estreitando pressionada prédios específicos e sub-redes onde o TCP é usado com mais frequência. Mais sub-relatórios romper o uso TCP por conferência e chamadas de duas partes.

![Captura de tela de um gráfico mostrando o número de fluxos de áudio de TCP por mês](media/quality-of-experience-review-guide-image23.png)

_Figura 23 – fluxos de áudio com o uso TCP_

##### <a name="investigation"></a>Investigação

Este relatório de gráfico exibe o uso TCP geral da sua organização. Usando este relatório, você pode responder às seguintes perguntas:

1.  Qual é o volume total de chamadas TCP para o mês atual?

2.  É melhor do que o mês anterior ou de pior?

3.  É a tendência de uso do TCP aumentando, steady, ou diminuindo?

Se notar que a tendência de uso do TCP está aumentando ou acima de utilização monthly normal, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. O ideal é que você deseja, no mínimo com base em TCP sessões de áudio possível na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Este relatório de tabela identifica o volume de TCP versus relatórios sobre o mês mais recente para conferências de áudio, vídeo e vídeo-based (VBSS) de compartilhamento de tela de uso do UDP.

![Relatório mostrando o volume de TCP versus fluxos de conferência UDP, com PCR mostrado na comparação](media/quality-of-experience-review-guide-image24.png)

_Figura 24 – TCP versus UDP - conferência_

##### <a name="analysis"></a>Análise

Embora você deseja o uso TCP ao ser tão baixa quanto possível, talvez você veja um pouco de uso TCP em uma implantação do contrário íntegro. Para comparar UDP com o uso TCP, divida fluxos de áudio de TCP por fluxos de áudio de UDP para determinar uma porcentagem. Um valor de mais de 1% precisa ser investigados ainda mais.

No exemplo acima, pegamos 1,806 fluxos TCP divididos por 10,481 fluxos UDP chegar a um valor de 17.2%. Esse valor é bem acima % 1 e nos diz que precisamos continuar nossa investigação para determinar onde o uso TCP está ocorrendo.

Também é incluída no relatório é a porcentagem de áudio ruim. Isso proporciona um modo de exibição para a comparação de qualidade da chamada entre UDP e TCP para ajudar a visualizar como TCP está afetando a qualidade da chamada overcall.

Então agora que você determinou que não há um alto uso de áudio com base em TCP em sua organização, o que fazer em seguida? Vá para os relatórios de **fluxos TCP Construindo e sub-rede** para dividir o uso TCP pelo construção e sub-redes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Fluxos TCP Construindo e sub-rede

Nos modelos de CQD fornecidos, vá para os fluxos TCP por sub-rede e criação de relatórios de tabela usando o gerenciada ou modelo de todas as redes. Há três relatórios incluídos no modelo, um para investigando conferência, com e sem informações de retransmissão da Microsoft e outro para investigando chamadas de duas partes. Para fins de investigar o uso TCP, o processo é a mesma, portanto focaremos a discussão na conferência somente.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendável poderão rapidamente distinguir dentro de fluxos de áudio externos ao olhar para uso TCP. 

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                                  |

![Relatório que lista os fluxos TCP, organizados por construir, rede e sub-rede por mês.](media/quality-of-experience-review-guide-image25.png)

_Figura 25 – TCP fluxos, criando - e sub-rede conferência_

##### <a name="remediation"></a>Remediação

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o volume de uso do TCP. Um relatório adicional também está incluído para identificar o IP de retransmissão Microsoft que foi usado na chamada para ajudar a isolar ausentes regras de firewall. Concentre os esforços de remediação nesses prédios que têm o maior volume de fluxos de áudio para maximizar o impacto.

A causa mais comum de uso do TCP está faltando regras de exceção no firewalls ou proxies. Voltaremos falando proxies na próxima seção, portanto por enquanto concentrar os esforços nos firewalls. Usando o edifício ou sub-rede fornecido, você pode determinar o firewall que precisa ser atualizado.

_Tabela 10 - remediação * orientação para fluxos TCP Construindo e sub-rede_

| Remediação        | Orientação     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar o firewall | Verifique se [as portas de IP do Office 365 e endereços](https://aka.ms/o365ips) são excluídos do seu firewall. Embora haja muitos endereços IP e portas que precisam ser aberto, problemas relacionados a mídia TCP, concentrar os esforços iniciais no seguinte: Verifique se as seguintes [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) estão em suas regras de firewall. Referir-se a linha 4 na tabela mostrada para obter informações de sub-rede de mídia específicos. [As portas UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): essas portas são as portas de mídia preferencial e devem ser abertas, caso contrário, o cliente falhará volta para a porta TCP 443. |
| Verifique se             | Use a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas de conectividade para portas e endereços IP do Office 365 específicos do edifício afetado ou sub-rede.    |

### <a name="investigate-http-proxy-usage"></a>Investigue o uso do proxy HTTP

Os proxies HTTP não é o caminho preferido para estabelecer sessões de mídia, para uma infinidade de motivos. Muitas contêm recursos de inspeção de pacotes profunda que pode impedir conexões ao serviço sejam concluídas e introduzir interrupções causadas. Além disso, os proxies talvez forçar TCP em vez de permitindo UDP, que é recomendado para melhor qualidade de áudio.

É sempre a recomendação da Microsoft para configurar o cliente para conectar-se diretamente a equipes e Skype para serviços corporativos. Isso é especialmente importante para o tráfego de mídia-based.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Fluxos de áudio com o uso de proxy HTTP geral

Este relatório descreve o uso de proxy ao longo do tempo em uma escala mensal. O relatório de fluxo de proxy HTTP nesta seção do modelo é muito semelhante os relatórios TCP. Ele não parece estar em estejam de chamadas ruins ou BOM, mas se a chamada é conectada por HTTP.

![Captura de tela dos fluxos de áudio com o relatório de uso do Proxy HTTP no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image26.png)

_Figura 26 – fluxos de áudio com o uso de Proxy HTTP_

##### <a name="analysis"></a>Análise

Se você vir um alto volume de uso do HTTP, consulte sua equipe da rede para garantir que as exclusões adequadas estejam em vigor para que os clientes são roteamento diretamente para equipes ou Skype para sub-redes de mídia Business Online. Idealmente, não deve haver nenhum uso do HTTP exibido aqui.

Se você tiver apenas um proxy de internet em sua organização, verifique as adequadas [URLs do Office 365 e exclusões de intervalo de endereços IP](https://aka.ms/o365ips). Se mais de um proxy de internet está configurado em sua organização, aproveitar o HTTP sub-recursos relatado para isolar qual construção ou sub-rede é afetado.

Para organizações que não é possível ignorar o proxy, certifique-se que o Skype para o cliente de negócios está configurado para entrar em corretamente quando ela está localizada atrás de um proxy conforme descrito no artigo [Skype para negócios deve usar servidor proxy para entrar em vez de tentar direta conexão](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Fluxos de proxy HTTP Construindo e sub-rede

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o uso do HTTP.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                        |

![Captura de tela do uso do Proxy HTTP pelo relatório de criação e a sub-rede em que o painel de controle de qualidade de chamada.](media/quality-of-experience-review-guide-image27.png)

_Figura 27 – sub-rede e uso de Proxy HTTP, criando_

##### <a name="remediation"></a>Remediação

Concentre os esforços de remediação em qualquer prédios ou as sub-redes com o uso de proxy HTTP. A causa mais comum de uso do HTTP está faltando regras de exceção de proxies. Usando o edifício ou sub-rede fornecido, você pode determinar qual proxy precisa ser atualizado.

Verifique se os [FQDNs do Office 365](https://aka.ms/o365ips) de necessários são excluídos do seu proxy.

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção se concentra nas tarefas de relatórios sobre o Skype para versões do cliente de negócios – específicas e o uso de dispositivos de certificados.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia. Consulte a descrição do relatório individual para obter mais informações. 


### <a name="determine-client-versions"></a>Determinar as versões do cliente

O relatório neste espaço enfoca identificando Skype para versões do cliente de negócios em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio de rede conteúdo de entrega Azure (CDN) e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.

Números de versão do Skype para negócios 2015 e 2016 podem ser encontrados por meio de links a seguir:

-   [Liberações de canal de atualização de cliente Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versão e compilação do Office 365 para clique para executar](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para downloads de negócios e atualizações](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.  

> [!IMPORTANT]
> Relatórios de cliente exigem que você excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. |

![Captura de tela do relatório de cliente e dispositivos no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image28.png)

_Figura 28 - relatório da versão de cliente_

#### <a name="remediation"></a>Remediação

Uma parte importante de dirigir experiências do usuário de alta qualidade é garantir que os clientes de gerenciada estão executando versões atualizadas do Skype para negócios. Isso oferece vários benefícios, entre eles:

-   É mais fácil gerenciar algumas versões versus muitas versões.

-   Ele fornece um nível de consistência da experiência.

-   Ele facilita a solucionar problemas de qualidade de chamada e usabilidade.

-   A Microsoft dá continuamente aperfeiçoamentos gerais e as otimizações em todo o produto. Garantir que os usuários recebam essas atualizações reduz os riscos de executar um problema que já foi resolvido.

Limitar sua implantação para as versões do cliente que são menos de seis meses, melhorar a experiência geral do usuário e melhorar a capacidade de gerenciamento em comparação a ter grandes números de diferentes versões do cliente no mesmo ambiente.

Se você estiver usando somente Office Click-to-Run, você estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional será necessária.

If, como a maioria das organizações, você tem uma mistura de pacotes Click-to-Run e installer (MSI), você pode usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Concentre seus esforços nesses clientes onde o volume está acima da média. Se você observar que os clientes são atrasado, trabalhar com a equipe responsável pelo gerenciamento de atualizações do Office e garantir que eles estiver aprovando e Implantando patches de cliente regularmente.

### <a name="devices-investigations"></a>Investigações de dispositivos

Para tornar use destes relatórios dispositivo, é melhor entender o conceito de médio de opinião pontuação (MOS). MOS é a medida padrão ouro para medir a qualidade de áudio perceptivelmente. Ele é representado como uma classificação de inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade de voz. Como ela é afetada pela percepção humana, é naturalmente subjetiva. Existem várias metodologias diferentes para testar subjetiva.
A maioria das medidas de qualidade de voz são baseados em uma escala de classificação (ACR) categorização absoluta.

Em um teste subjetivo ACR, um número significativo de estatística de pessoas classificar seu qualidade da experiência em uma escala de 1 (ruim) a 5 (excelente). A média das pontuações é o MOS. O MOS resultante depende do intervalo de experiências que foram expostos ao grupo e ao tipo de experiência sendo classificada como.

Porque ele é impraticável para conduzir testes subjetivas de qualidade de voz para um sistema de comunicação em tempo real, equipes e Skype para negócios geram valores MOS usando algoritmos avançados objetivamente prever os resultados de um teste subjetiva.

O conjunto disponível de MOS e métricas associadas fornecem um modo de exibição para a qualidade da experiência de ser entregue aos usuários.

Fornecendo aos usuários com dispositivos certificados para equipes e Skype for Business, você reduz a probabilidade de encontrando experiências negativas devido ao próprio dispositivo (que é mais provável, por exemplo, com microfones e alto-falantes laptop internas). Para obter mais informações, consulte [telefones e dispositivos para Skype para negócios](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso organizacional dos dispositivos de captura (microfones) por volume

Este relatório é usado para avaliar o uso de microfone por volume e de pontuação do MOS e pode ser encontrado nos modelos acompanha em clientes e dispositivos *.*

> [!IMPORTANT]
> Relatórios de dispositivo exigem que você poderá excluir dados participantes federados. Para excluir dados de participante federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. 

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.<br><br> Você poderá observar quando visualizem esse relatório que você veja o mesmo dispositivo relatado várias vezes. Isso acontece devido à maneira como o dispositivo é informado de serem reportados para CQD. Diferenças de hardware e de localidade do sistema operacional relatar dados do dispositivo de forma diferente.

![Captura de tela do relatório de dispositivos (microfone) no painel de qualidade de chamada.](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – relatório de dispositivo (microfone)_

##### <a name="remediation"></a>Remediação

A primeira tarefa é determinar o alvo de MOS que você gostaria de obter. Intervalo de 1 a 5, com 5 sendo o melhor de pontuações MOS. Escolha um destino razoável, com base em seu ambiente e os resultados da consulta. No exemplo a seguir, o destino será uma pontuação do MOS de 3.6 ou superior para todos os dispositivos que tenham mais de 100 fluxos. Você obterá a qualidade do dispositivo de destino quando:

-   Os resultados da consulta de dispositivo retornam MOS \> 3.6 para NumStreams \> 100

Normalmente, você precisará substituir dispositivos com desempenho insatisfatório por dispositivos de certificados. Algumas considerações quando analisando o relatório de dispositivo incluem:

-   São dispositivos certificados ou conhecidos para ser boas em seu ambiente? Se um dispositivo de certificados ou boa é retornado na consulta com uma pontuação do MOS inferior que sua linha de base, pode haver desconhecidos fatores adicionais (por exemplo, uma rede ruim ou pc capacidade suficiente) que está contribuindo para a pontuação baixa.
    Investigação adicional será necessária.

-   Você pode identificar os usuários de um dispositivo por meio da [Análise de chamada](#call-analytics-training). Verifique para garantir que eles têm os drivers de dispositivo mais recentes e que seu dispositivo não está conectado por meio de um hub USB.

-   Verificar se há uma correlação entre dispositivos ruim e tornar um determinado do sistema e modelo. Em caso afirmativo, o dispositivo talvez não seja compatível ou precisa de atualizações de driver.

A segunda tarefa é determinar o uso geral de dispositivos não-certificados. É recomendável que pelo menos de 80 por cento de todos os fluxos de áudio de usar um dispositivo de certificados.
Isso é realizado melhor exportando o relatório de dispositivos para o Excel e manualmente Calculando o uso de dispositivos de certificados ou aprovados. As organizações geralmente manter uma lista de todos os dispositivos aprovados, para que filtragem e classificação dos dados devem ser simples.

## <a name="appendix-a-lync-networking-guide"></a>Guia de rede do apêndice Lync r.

Para obter mais informações em equipes e Skype para conceitos de rede de negócios e o raciocínio por trás de sua importância a qualidade, o [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) é aplicável.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de desempenho do apêndice B. rede

A qualidade de mídia em tempo real (áudio, vídeo e compartilhamento de aplicativos) sobre IP significativamente é afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter melhor equipes ou Skype para qualidade de mídia de negócios, sua rede deve atender aos seguintes métricas de desempenho de rede.

_A tabela 11 - requisitos de desempenho de rede_

| Métrica                           | Cliente para o Microsoft Edge           | Edge do cliente para o Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latência (uma maneira)                | \<50 ms                            | \<30 ms                            |
| Latência (tempo de resposta ou tempo de ida e volta) | \<100 ms                           | \<60 ms                            |
| Perda de pacotes de intermitência                | \<10% durante qualquer intervalo de 200 ms   | \<1% durante qualquer intervalo de 200 ms    |
| Perda de pacote                      | \<1% durante qualquer intervalo de 15 segundos    | \<0,1% durante qualquer intervalo de 15 segundos  |
| Tremulação de entre chegada de pacotes      | \<30 ms durante qualquer intervalo de 15 segundos | \<15 ms durante qualquer intervalo de 15 segundos |
| Reordenar de pacotes                   | \<% de 0,05 pacotes de fora de ordem       | \<pacotes de fora de ordem 0,01%      |

Para obter mais informações, consulte o artigo a seguir sobre o [desempenho de rede e qualidade de mídia](https://aka.ms/performancerequirements) para equipes e Skype para negócios Online.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apêndice C. Outros recursos

### <a name="building-data-file"></a>Criando o arquivo de dados

-   [Ativando e usar CQD no Skype para negócios Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Treinamento de CQD

-   <https://aka.ms/sof-cqd>

-   Guia de [Introdução ao CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) e workshop.

-   [Guia on-line CQD dimensões e medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Treinamento de análise de chamada

-   [Apresentando a análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar a Análise de Chamada do Skype for Business](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Qual é a diferença entre a Análise de Chamada e o Painel de Qualidade de Chamadas?](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas no Skype for Business](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Suporte de análise de chamada

-   Comunidade: [Skype para o programa de visualização de negócios](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Para obter suporte, entrar em nosso portal de visualização [www.skypepreview.com](http://www.skypepreview.com), selecione **um problema de relatório**e usar a opção **Criar novo Bug** para relatar algum problema. Observe que os engenheiros de suporte estão disponíveis para oferecer suporte de segunda à sexta-feira, entre os horários de 6 horas para 9 PM EST. Solicitações fora essas horas serão priorizadas do dia seguinte.

### <a name="devices"></a>Dispositivos

-   [Skype para soluções de negócios pessoais periféricos & PCs de catálogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Relatórios de locatário

-   [Pacote de conteúdo de adoção do Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Relatórios do Skype for Business Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Relatórios de Teams da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
