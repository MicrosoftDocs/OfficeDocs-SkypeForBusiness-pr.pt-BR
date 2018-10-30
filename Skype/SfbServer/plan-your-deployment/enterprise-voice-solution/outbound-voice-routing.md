---
title: Planejar o roteamento de voz de saída em Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Saiba mais sobre o roteamento de voz de saída em Skype para Business Server Enterprise Voice, incluindo configurações de roteamento de chamada, planos de discagem, regras de normalização, políticas de voz, registros de uso PSTN e roteamentos de voz.
ms.openlocfilehash: 8b7ef6c4e07bd7618645606c777b257e1d32691f
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838813"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planejar o roteamento de voz de saída em Skype para Business Server
 
Saiba mais sobre o roteamento de voz de saída em Skype para Business Server Enterprise Voice, incluindo configurações de roteamento de chamada, planos de discagem, regras de normalização, políticas de voz, registros de uso PSTN e roteamentos de voz.
  
Roteamento de chamadas de saída se aplica às chamadas do Enterprise Voice destinadas a um gateway PSTN (rede) telefônica pública comutada, tronco ou privada Central de comutação telefônica (PBX). Quando um Skype para comercial do usuário faz uma chamada, o servidor normaliza o número de telefone para o formato e. 164, se necessário e tenta associá-lo a um URI do SIP. Se o servidor não conseguir fazer a correspondência, ele aplicará a lógica de roteamento de chamadas de saída com base na cadeia de caracteres de discagem fornecida. Especifique essa lógica definindo as configurações do servidor descritas na tabela a seguir.
  
**Configurações do roteamento de chamadas de Skype para saída do servidor de negócios**

|**Objeto**|**Descrição**|
|:-----|:-----|
|Plano de discagem  <br/> |Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um único formato padrão (E.164) para fins de roteamento de chamadas e autorização de telefones.  <br/> |
|Regra de normalização  <br/> |As regras de normalização definem como os números de telefone expressos em vários formatos são roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de maneira diferente, dependendo do local do qual é discada e da pessoa ou do objeto de contato que está fazendo a chamada. Um conjunto de regras de normalização associadas a um local específico constitui um plano de discagem.  <br/> |
|Política de voz  <br/> |Uma política de voz associa um ou mais registros de uso de PSTN a um usuário ou grupo de usuários. Também fornece uma lista de recursos de chamada que você pode ativar ou desativar.  <br/> |
|Registro de uso de PSTN  <br/> |Um registro de uso de PSTN especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização.  <br/> |
|Rota de chamada  <br/> |Uma rota de chamada associa os números de telefone de destino com troncos específicos e registros de uso de PSTN. Um gateway PSTN é considerado um tronco.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Planos de discagem e regras de normalização

Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um único formato padrão (E.164) para fins de roteamento de chamadas e autorização de telefones. 
  
As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado. A mesma sequência de discagem pode ser interpretada e convertida de forma diferente dependendo do local do qual ele é discado e da pessoa ou do objeto de contato que está fazendo a chamada.
  
### <a name="dial-plan-scope"></a>Escopo do plano de discagem

O escopo de um plano de discagem determina o nível hierárquico em que o plano de discagem pode ser aplicado. Skype para Business Server, um usuário pode ser atribuído um plano de discagem por usuário específico. Se não for atribuído a um plano de discagem do usuário, o plano de discagem do pool de Front-End será aplicado. Se não houver nenhum plano de discagem do pool de Front-End, o plano de discagem do site será aplicado. Finalmente, se não houver nenhum outro plano de discagem aplicável ao usuário, o plano de discagem global será aplicado.
  
Os clientes obtêm os níveis de escopo de plano de discagem por meio de configurações de provisionamento em banda que são fornecidas quando os usuários façam logon no Skype para negócios. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o Skype para painel de controle do servidor de negócios.
  
> [!NOTE]
> O plano de discagem de gateway PSTN (Rede Telefônica Pública Comutada) em nível de serviço é aplicado às chamadas de entrada de um gateway específico. 
  
Os níveis de escopo do plano de discagem são definidos como a seguir:
  
- **Plano de discagem do usuário**: pode ser atribuído a usuários individuais, grupos ou objetos de contato. Os aplicativos de voz podem pesquisar um plano de discagem por usuário quando uma chamada é recebida com o contexto de telefone definido para padrão do usuário. Para atribuir um plano de discagem, um objeto de contato é tratado como um usuário individual.
    
- **Plano de discagem do pool**: pode ser criado no nível de serviço para qualquer gateway PSTN ou Registrador Avançado na sua topologia. Para definir um plano de discagem do pool, você deve especificar o serviço (gateway PSTN ou pool do Registrador Avançado) ao qual o plano de discagem se aplica. 
    
- **Plano de discagem do local**: pode ser criado para todo o local, exceto para qualquer usuário, grupo ou objeto de contato ao qual é atribuído um plano de discagem do pool ou um plano de discagem do usuário. Para definir um plano de discagem do local, você deve especificar o local ao qual o plano de discagem é aplicado.
    
- **Plano de discagem global**: é o plano de discagem padrão instalado com o produto. É possível editar o plano de discagem global, mas não excluí-lo. Este plano de discagem se aplica a todos os usuários do Enterprise Voice, grupos e objetos de contato na sua implantação, a menos que você configure e atribua um plano de discagem com um escopo mais específico.
    
### <a name="planning-for-dial-plans"></a>Planejamento de planos de discagem

Para planejar uma discagem, siga estas instruções:
  
- Liste todas as localidades nas quais a organização tem escritórios.
    
    A lista deve estar atualizada e ser completa. Precisará ser revisada conforme a organização da empresa evolui. Em uma grande empresa multinacional com várias filiais pequenas, isso pode ser uma tarefa demorada.
    
- Identifique padrões de números válidos para cada local.
    
    A parte mais demorada do planejamento de seus planos de discagem é identificar os padrões de números válidos para cada local. Em alguns casos, será possível copiar as regras de normalização gravadas para um plano de discagem a outros planos de discagem, especialmente se os locais correspondentes estão dentro do mesmo país/região ou continente. Em outros casos, as pequenas alterações em números em um plano de discagem podem ser suficientes para usá-los em outros planos de discagem.
    
- Desenvolva um esquema em toda a organização para nomear os planos de discagem.
    
    Adotar um esquema de nomeação padrão garante a consistência em toda a organização e facilita a manutenção e as atualizações.
    
- Decida se vários planos de discagem são necessários para um único local. 
    
    Se sua organização mantenha um único plano de discagem em vários locais, você ainda precisará criar um plano de discagem separado para usuários do Enterprise Voice que estiver migrando de uma central privada (PBX) e quem precisa ter suas extensões existentes retidos.
    
- Decida se os planos de discagem por usuário são necessários. Por exemplo, se você tiver usuários em um site de filial que são registrados com o site central, ou se você tiver usuários que estão registrados em um aparelho de filial, você pode considerar especiais cenários de discagem para tais usuários usando por usuário planos de discagem e regras de normalização . Para obter detalhes, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determine o escopo do plano de discagem (como descrito anteriormente neste tópico).
    
Para criar um plano de discagem, especifique valores nos seguintes campos, conforme necessário, usando-se Skype para painel de controle de servidor de negócios ou Skype para Business Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Nome e nome simples

Para planos de discagem do usuário, você deve especificar um nome descritivo que identifique os usuários, os grupos ou os objetos de contato aos quais o plano de discagem será atribuído. Para planos de discagem de local, o campo Nome é pré-preenchido com o nome do local e não pode ser alterado. Planos de discagem para o pool, o campo nome é pré-preenchido com o gateway PSTN ou pool de Front-End totalmente qualificado (FQDN) do nome de domínio e não pode ser alterada.
  
O nome simples do plano de discagem é pré-preenchida com uma cadeia de caracteres que é derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite a criação de uma convenção de nomenclatura mais descritiva para os planos de discagem. Nome do TheSimple valor não pode estar vazio e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para toda a empresa e usar essa convenção consistentemente em todos os locais e usuários.
  
#### <a name="description"></a>Descrição

Recomendamos que você digite o nome comum reconhecível da localização geográfica à qual se aplica o plano de discagem correspondente. Por exemplo, se o nome do plano de discagem for Londres.Contoso.com, a descrição recomendada será Londres. 
  
#### <a name="dial-in-conferencing-region"></a>Região da conferência discada

Se você estiver implantando a conferência discada, precisará especificar uma região de conferência de discagem para associar os números de acesso da conferência discada com um plano de discagem. 
  
#### <a name="external-access-prefix"></a>Prefixo de acesso externo

Você pode especificar um prefixo de acesso externo de até quatro caracteres (#, \*e 0-9) se os usuários precisam discar de um ou mais líderes dígitos adicionais (por exemplo, 9) para obter uma linha externa.
  
> [!NOTE]
> Se você especificar um prefixo de acesso externo, não precisará criar uma regra de normalização adicional para acomodar o prefixo. 
  
### <a name="normalization-rules"></a>Regras de normalização

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para o local nomeado. A mesma cadeia numérica pode ser interpretada e convertida de forma diferente dependendo do local no qual ela é discada. As regras de normalização são necessárias para o roteamento de chamada porque os usuários podem, e devem, usar vários formatos ao inserir números de telefone em suas listas de contatos.
  
A normalização de números de telefone fornecidos pelo usuário oferece um formato consistente que facilita as tarefas a seguir:
  
- Corresponde um número discado com o URI do SIP do destinatário.
    
- Aplicar regras de autorização de discagem ao chamador.
    
Estes são alguns dos campos numéricos que as regras de normalização talvez precisem considerar:
  
- Plano de discagem
    
- Código do país
    
- Código de área
    
- Tamanho da extensão
    
- Prefixo do local
    
#### <a name="creating-normalization-rules"></a>Criando regras de normalização

As regras de normalização usam expressões regulares do .NET Framework para especificar padrões de correspondência numérica que o servidor usa para converter cadeias de caracteres de discagem no formato E.164 para fins de pesquisa de número inverso. Você cria regras de normalização no Skype para painel de controle do Business Server inserindo as expressões manualmente, ou inserindo inicial dígitos e o tamanho das cadeias de caracteres de discagem a ser correspondido e deixar o Skype para painel de controle do servidor de negócios Gere a expressão regular correspondente para você. Em qualquer um desses casos, ao terminar, você poderá inserir um número de teste para verificar se a regra de normalização funciona como esperado.
  
Para obter detalhes sobre como usar expressões regulares do .NET Framework, consulte ["expressões regulares do .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Exemplos de regras de normalização
<a name="BKMK_SampleNormalizationRules"> </a>

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.
  
**Tabela 1. Regras de normalização usando expressões regulares do .NET Framework**

|**Nome da regra**|**Descrição**|**Padrão de número**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte extensões de 4 dígitos  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos  <br/> |^ 5(\d{4})$  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos em números locais de Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/> |
|7digitcallingDallas  <br/> |Converte números de 7 dígitos em números locais de Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 é convertido em +19725550100  <br/> |
|10digitcallingUS  <br/> |Converte números de 10 dígitos nos Estados Unidos  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 é convertido em +12065550100  <br/> |
|LDCallingUS  <br/> |Converte números com prefixos de longa distância nos Estados Unidos  <br/> |^ 1(\d{10})$  <br/> |+$1  <br/> |12145550100 é convertido em +2145550100  <br/> |
|IntlCallingUS  <br/> |Converte números com prefixos internacionais nos Estados Unidos  <br/> |^ 011(\d\*)$  <br/> |+$1  <br/> |01191445550100 é convertido em +91445550100  <br/> |
|RedmondOperator  <br/> |Converte 0 no operador de Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Redmond (222)  <br/> |^ 6222(\d{4})$  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|NYSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Nova York (333)  <br/> |^ 6333(\d{4})$  <br/> |+1202555$1  <br/> |63330100 é convertido em +12025550100  <br/> |
|DallasSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Dallas (444)  <br/> |^ 6444(\d{4})$  <br/> |+1972555$1  <br/> |64440100 é convertido em +19725550100  <br/> |
   
A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, com base nas regras de normalização mostradas na tabela anterior.
  
**Tabela 2. Plano de discagem de Redmond com base em regras de normalização mostradas na Tabela 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma opção. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido. 
  
## <a name="voice-policies"></a>Políticas de voz

Skype Business Server políticas de voz definem o seguinte para cada usuário, site ou organização que recebeu a política:
  
- Um conjunto de recursos que podem ser habilitados ou desabilitados para disponibilizar a funcionalidade do Enterprise Voice disponível para usuários de chamada.
    
- Um conjunto de registros de uso de PSTN (Rede Telefônica Pública Comutada) que define quais tipos de chamadas são autorizadas. 
    
As etapas a seguir o ajudarão a planejar as políticas de voz que você precisará para implantação do Enterprise Voice:
  
- Determine como você configurará sua política de voz global (a política de voz padrão instalada com o produto). Essa política se aplicará a todos os usuários do Enterprise Voice que não são explicitamente atribuídos uma política de nível de site ou por usuário.
    
- Identifique as políticas de voz em nível de local das quais você possa precisar.
    
- Identifique as políticas de voz por usuário que você possa precisar.
    
- Decida quais recursos de chamada serão habilitados para cada política de voz.
    
- Determine quais registros de uso de PSTN configurar para cada política de voz.
    
### <a name="voice-policy-scope"></a>Escopo da política de voz

O escopo da política de voz determina o nível hierárquico no qual a política pode ser aplicada. Skype para Business Server, você pode configurar políticas de voz com os seguintes níveis de escopo (listadas da mais específica para o mais geral).
  
- A **política de voz de usuário** pode ser atribuída a usuários individuais, grupos ou objetos de contato. Essa á política de nível mais baixo. As políticas de voz de usuário podem ser implantadas para habilitar recursos para determinados usuários ou grupos em um local, mas não para outros no mesmo local. Por exemplo, talvez você queira desabilitar a discagem de longa distância para alguns funcionários. Para a finalidade de atribuição de uma política de voz, um objeto de contato será tratado como um usuário individual.
    
    > [!NOTE]
    > Recomendamos que você implante uma política de voz de usuário para usuários que estão registrados em um aparelho de filial persistente ou usuários de Enterprise Voice de site da filial que são registrados com a implantação do site central. 
  
- A **política de voz de local** é aplicada a todo o local, exceto para quaisquer usuários, grupos ou objetos de contato que recebam uma política de voz de usuário. Para definir uma política de voz de local, você precisa especificar o local ao qual a política será aplicada. Se uma política de voz de usuário não tiver sido atribuída, a política de voz de local será usada.
    
- A **política de voz global** é a política de voz padrão, instalada com o produto. É possível editar a política de voz global para atender às necessidades específicas de sua organização, mas não é possível renomeá-la ou excluí-la. Essa política de voz se aplica a todos os usuários do Enterprise Voice, grupos e objetos de contato em sua implantação, a menos que você configure e atribua uma política de voz com escopo mais específica. Se você quiser desabilitar totalmente essa política, certifique-se de que todos os locais e usuários tenham políticas personalizadas atribuídas a eles.
    
### <a name="call-features"></a>Recursos de chamada

É possível habilitar ou desabilitar os recursos de chamada a seguir para cada política de voz:
  
- O **encaminhamento de chamadas** permite que os usuários encaminhem chamadas para outros telefones e dispositivos cliente. Habilitado por padrão.
    
- A **delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Habilitado por padrão.
    
- A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
- O **estacionamento de chamada** permite que os usuários estacionem chamadas e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
- O **toque simultâneo** permite que as chamadas de entrada toquem em um telefone adicional (por exemplo, um celular) ou outros dispositivos do ponto de extremidade. Habilitado por padrão.
    
- A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.
    
- O **redirecionamento de PSTN** permite que as chamadas feitas pelos usuários que receberam essa política para outros usuários corporativos sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.
    
- A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamadas de um usuário específico. Desabilitada por padrão.
    
- **Mal-intencionado ligue para rastreamento** permite que os usuários denunciar chamadas mal-intencionadas usando o Skype para o cliente de negócios e, em seguida, sinalizadores dessas chamadas em que os registros de detalhes da chamada. Desabilitado por padrão.
    
- **Escape de caixa postal** evita que as chamadas imediatamente sendo roteados para o sistema de caixa postal do telefone celular do usuário, quando o toque simultâneo é configurado e o telefone estiver desativado, fora da bateria ou fora do intervalo e se baseia em um valor de timer. Essa configuração habilita e desabilita o temporizador e define o valor dele. Ela pode ser configurada somente por meio do Skype do Shell de gerenciamento do servidor de negócios. Desabilitado por padrão.
    
- **Usos da PSTN toques simultâneos e de encaminhamento de chamadas** permite que os administradores especifiquem o uso da PSTN mesmo como a política de voz para encaminhamento de chamadas e toque simultâneo, restringir o encaminhamento de chamadas e toque simultâneo para Skype interno para Somente, usuários comerciais ou especifique um uso PSTN personalizado que seja diferente do uso de PSTN da política de voz. O padrão é usar a PSTN da mesma forma que a política de voz para encaminhamento de chamadas e toque simultâneo.
    
### <a name="pstn-usage-records"></a>Registros de uso de PSTN

Cada política de voz deve ter um ou mais registros de uso de PSTN associados. Os usos de PSTN podem ser associados a uma política de voz somente para toque simultâneo e encaminhamento de chamadas. 
  
> [!NOTE]
> A ordem de uso de PSTN é fundamental, pois, o se comparar usuários a rotas, a funcionalidade de roteamento de saída compara as utilizações de PSTN do início ao fim. Se o primeiro uso corresponder à rota da chamada, essa rota será usada. Caso contrário, a funcionalidade de roteamento de saída analisará o próximo uso de PSTN na lista e continuará até que uma correspondência seja encontrada. Na verdade, os usos de PSTN subsequentes fornecerão backup se o primeiro da lista não estiver disponível. 
  
## <a name="pstn-usage-records"></a>Registros de uso de PSTN

O planejamento dos registros de uso de PSTN consiste principalmente em listar todas as permissões de chamadas em uso na organização, desde o CEO até os funcionários temporários, os consultores e a equipe contingente. Esse processo também oferece uma oportunidade de reexaminar as permissões de chamadas existentes e revisá-las. Você pode criar registros de uso PSTN somente para essas permissões de chamada que se aplicam aos usuários do Enterprise Voice previstos, mas uma solução melhor longo alcance pode ser a criação de registros de uso do PSTN para todas as permissões de chamada, independentemente se alguns talvez não estejam atualmente aplica-se ao grupo de usuários a serem habilitados para o Enterprise Voice. Se as permissões de chamada forem alteradas ou novos usuários com permissões de chamada diferentes forem adicionados, você já terá criado os registros de uso de PSTN necessários.
  
A tabela a seguir mostra um quadro típico de uso de PSTN.
  
**Registros de uso de PSTN**

|**Atributo do telefone**|**Descrição**|
|:-----|:-----|
|Local  <br/> |Chamadas locais  <br/> |
|Long-Distance  <br/> |Chamadas interurbanas  <br/> |
|International  <br/> |Chamadas internacionais  <br/> |
|Delhi  <br/> |Funcionários de Délhi em tempo integral  <br/> |
|Redmond  <br/> |Funcionários de Redmond em tempo integral  <br/> |
|RedmondTemps  <br/> |Funcionários temporários de Redmond  <br/> |
|Zurich  <br/> |Funcionários de Zurique em tempo integral  <br/> |
   
Sozinhos, os registros de uso do PSTN não fazem nada. Para que funcionem, é necessário associá-los ao seguinte:
  
- Políticas de voz, que são atribuídas a usuários.
    
- Rotas, que são atribuídas a números de telefone.
    
## <a name="voice-routes"></a>Rotas de voz

As rotas de chamada especificam como Skype para Business Server trata as chamadas de saída feitas pelos usuários do Enterprise Voice. Quando um usuário disca um número, o servidor Front-End normaliza a cadeia de caracteres de discagem para o formato e. 164, se necessário e tenta associá-lo a um URI do SIP. Se o servidor não conseguir fazer a correspondência, ele aplicará a lógica de encaminhamento de chamadas realizadas com base no número. A etapa final na definição dessa lógica é a criação de uma rota de chamada nomeada separada para cada conjunto de números de telefone listados em cada plano de discagem.
  
Antes de definir as rotas das chamadas de saída, você deve concluir as seguintes etapas:
  
- Implantar um ou mais troncos.
    
- Criar planos de discagem conforme a necessidade para locais, indivíduos e objetos de Contato.
    
- Criar registros de uso de rede telefônica pública comutada (PSTN).
    
Além disso, para habilitar o roteamento de chamadas de saída, você deve criar e atribuir uma ou mais políticas de voz. Você pode fazer isso antes ou depois de definir as rotas das chamadas de saída.
  
Para cada rota, você deve especificar:
  
- Um nome pelo qual a rota possa ser facilmente identificada.
    
- Uma descrição opcional, caso apenas o nome não seja suficiente para descrevê-la.
    
- O padrão de correspondência da expressão regular que identifica os números de telefone de destino aos quais a rota será aplicada, junto com as exceções às quais o padrão de correspondência não será aplicado.
    
- Um ou mais troncos que você desejar atribuir à rota.
    
- Os registros de uso do PSTN que os usuários devem ter para fazer chamadas para números que correspondam à expressão regular do número de telefone de destino.
    
Você pode especificar as rotas de chamada no Skype para painel de controle do Business Server. Essas rotas preenchem a tabela de roteamento de servidor, que Skype para Business Server usa para rotear as chamadas destinadas a PSTN de chamada.
  
### <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Skype para Business Server oferece flexibilidade para como as chamadas são roteadas para o PSTN. Uma rota de voz especifica um conjunto de troncos à PSTN que podem ser usados para uma chamada de voz específica. Um tronco associa um servidor de mediação e um número de porta com um gateway PSTN e o número da porta de escuta. Essa associação lógica permite que um servidor de mediação ser associado com diversos gateways e ter várias conexões com o mesmo gateway. Ao definir uma rota de chamada, você especificar os troncos associados a essa rota, mas você não especificar quais servidores de mediação associados a rota. Para criar troncos definindo as relações entre os servidores de mediação e gateways PSTN, IP-PBXs e controladores de borda de sessão (SBCs), usam o construtor de topologias.
  
### <a name="least-cost-routing"></a>Roteamento de Custo Mínimo

A capacidade de especificar os troncos para os quais os diversos números são roteados permite determinar as rotas de menor custo e implementá-las adequadamente. A regra geral para selecionar troncos é escolher o tronco com o gateway mais próximo da localidade do número de destino para reduzir as tarifas de interurbano. Por exemplo, caso você esteja em Nova York telefonando para um número em Roma, a chamada seguiria pela rede IP até o tronco com o gateway no escritório de Roma e os custos seriam os de uma chamada local.
  
Para um exemplo de como o roteamento de custo mínimo poderia ser usado, considere o seguinte: a Fabrikam decide permitir que os usuários alemães façam chamadas para os números dos EUA usando o tronco norte-americano. Fabrikam também quer configurar o sistema de forma que todas as chamadas do Skype EUA para usuários corporativos Server Alemanha e países/regiões adjacentes encerrar no tronco com o gateway na Alemanha. Esse roteamento economizará dinheiro porque uma chamada da Alemanha para a Áustria, por exemplo, é mais barata do que uma chamada dos EUA para a Áustria.
  
### <a name="translating-outbound-dial-strings"></a>Como traduzir cadeias de caracteres de discagem de saída

Skype para Business Server requer que todos os discagem cadeias de caracteres para ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL). Para troncos com gateways ou privada de comutação telefônica (PBXs) que exigem números, traduzidos nos formatos de discagem local, Skype para Business Server permite que você crie um ou mais regras que ajudam na manipulação do número chamado (isto é, URI de solicitação) antes de roteá -lo ao tronco. Por exemplo, você pode escrever uma regra para remover +44 do início de uma cadeia de caracteres de discagem e subsituí-lo por 0144.
  
Com o Skype para Business Server, é possível criar uma ou mais regras que ajudam na manipulação do número chamado antes de roteá-lo ao tronco.
  
Ao planejar suas troncos que associar pares de gateway: porta pares: a porta do servidor de mediação, pode ser útil para troncos de grupo com local semelhante requisitos de discagem e, portanto, reduzir o número de regras de conversão necessária e o tempo que leva para gravá-los.
  
### <a name="configuring-caller-id"></a>Como configurar o ID de chamador

Skype para Business Server oferece uma maneira de manipular o ID do chamador para chamadas de saída. Por exemplo, se uma organização deseja mascarar extensões de discagem direta dos funcionários e substitua o genérico corporativo ou o número de departamento, um administrador pode fazer que usando Skype para painel de controle do servidor de negócios para suprimir a identificação do chamador e substituí-la com uma ID de chamador alternativo especificado. Ao planejar sua lógica de roteamento, considere quais indivíduos, grupos, sites, você vai querer essa opção para — talvez, até, para todos os funcionários.
  
> [!NOTE]
> Para chamadas reencaminhadas pela PSTN, o ID de chamador genérico será apresentado em vez do ID de chamador original. Isso pode fazer com que a chamada ignore configurações de Não Incomodar ou de privacidade que o receptor possa ter configurado. 
  
### <a name="additional-routing-logic"></a>Lógica de roteamento adicional

Ao criar rotas de chamadas de saída, você deve estar ciente dos seguintes fatores que podem afetar a lógica de roteamento:
  
- Onde uma chamada passa por uma fronteira federada, a parte do domínio do URI é usada para rotear a chamada até a empresa responsável por aplicar a lógica de roteamento de saída.
    
- Se a parte do domínio do URI de solicitação não contiver um domínio suportado para a empresa, o componente de roteamento de saída no servidor não processa a chamada.
    
- Se um usuário não estiver habilitado para o Enterprise Voice, o servidor aplicará outra lógica de roteamento, conforme apropriado.
    
- Se uma chamada for roteada para um gateway que está completamente ocupado (todas as linhas do tronco estão ocupadas), o gateway rejeitará a chamada e a lógica de roteamento de saída a reencaminhará para a próxima rota de menor custo. Considere isso cuidadosamente, porque um gateway dimensionado para um escritório pequeno no exterior (por exemplo, em Zurique) pode na verdade carregar um volume significativo de tráfego não local para chamadas internacionais para a Suíça. Se o gateway não for dimensionado corretamente para esse tráfego adicional, as chamadas para a Suíça poderão ser encaminhadas por um gateway na Alemanha, resultando em tarifas maiores.
    

