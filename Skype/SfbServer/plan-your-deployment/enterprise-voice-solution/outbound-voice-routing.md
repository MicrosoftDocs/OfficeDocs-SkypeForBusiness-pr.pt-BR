---
title: Planejar o roteamento de voz de saída Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Saiba mais sobre roteamento de voz de saída em Skype for Business Server Enterprise Voice, incluindo configurações de roteamento de chamadas, planos de discagem, regras de normalização, políticas de voz, registros de uso de PSTN e rotas de voz.
ms.openlocfilehash: 47b0b196579d69612c3c9d62c8ca9aade008535e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759503"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planejar o roteamento de voz de saída Skype for Business Server
 
Saiba mais sobre roteamento de voz de saída em Skype for Business Server Enterprise Voice, incluindo configurações de roteamento de chamadas, planos de discagem, regras de normalização, políticas de voz, registros de uso de PSTN e rotas de voz.
  
O roteamento de chamadas de saída se aplica Enterprise Voice chamadas destinadas a um gateway PSTN (rede telefônica pública comutado), tronco ou pbx (troca de filial privada). Quando um Skype for Business faz uma chamada, o servidor normaliza o número de telefone para o formato E.164, se necessário, e tenta corresponder a ele a um URI SIP. Se o servidor não conseguir fazer a correspondência, ele aplicará a lógica de roteamento de chamadas de saída baseada na cadeia de caracteres de discagem especificada. Especifique essa lógica definindo as configurações do servidor descritas na tabela a seguir.
  
**Skype for Business Server Roteamento de chamadas de saída Configurações**

|**Objeto**|**Descrição**|
|:-----|:-----|
|Plano de discagem  <br/> |Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização.  <br/> |
|Regra de normalização  <br/> |As regras de normalização definem como os números de telefone expressos em vários formatos são roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de maneira diferente, conforme o local do qual é discada e da pessoa ou objeto de contato que está fazendo a chamada. Um conjunto de regras de normalização associadas a um local específico constitui um plano de discagem.  <br/> |
|Política de voz  <br/> |Uma política de voz associa um ou mais registros de uso de PSTN a um usuário ou grupo de usuários. Também fornece uma lista de recursos de chamada que você pode ativar ou desativar.  <br/> |
|Registro de uso de PSTN  <br/> |Um registro de uso de PSTN especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização.  <br/> |
|Rota de chamada  <br/> |Uma rota de chamada associa os números de telefone de destino com troncos específicos e registros de uso de PSTN. Um gateway PSTN é considerado um tronco.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Planos de discagem e regras de normalização

Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização. 
  
As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e traduzida de forma diferente, dependendo do local do qual ela é discada e da pessoa ou objeto de contato que faz a chamada.
  
### <a name="dial-plan-scope"></a>Escopo do plano de discagem

O escopo de um plano de discagem determina o nível hierárquico no qual o plano de discagem pode ser aplicado. Em Skype for Business Server, um usuário pode ser atribuído a um plano de discagem específico por usuário. Se um plano de discagem do usuário não for atribuído, o plano de discagem do pool front-end será aplicado. Se não houver um plano de discagem de pool de Front-End, o plano de discagem do site será aplicado. Finalmente, se nenhum plano de discagem é aplicável para o usuário, o plano de discagem global é aplicado.
  
Os clientes obtém níveis de escopo do plano de discagem por meio de configurações de provisionamento em banda fornecidas quando os usuários fazem logoff Skype for Business. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando Skype for Business Server Painel de Controle.
  
> [!NOTE]
> O plano de discagem de gateway PSTN (rede telefônica pública comutado) de nível de serviço é aplicado às chamadas de entrada de um gateway específico. 
  
Os níveis de escopo do plano de discagem são definidos como a seguir:
  
- **Plano de discagem do** usuário : pode ser atribuído a usuários individuais, grupos ou objetos de contato. Os aplicativos de voz podem procurar um plano de discagem por usuário quando uma chamada é recebida com o contexto de telefone definido como padrão do usuário. Para atribuir um plano de discagem, um objeto de contato é tratado como um usuário individual.
    
- **Plano de discagem do pool**: pode ser criado no nível de serviço para qualquer gateway PSTN ou Registrador na sua topologia. Para definir um plano de discagem do pool, você deve especificar o serviço (gateway PSTN ou pool do Registrador) ao qual o plano de discagem se aplica. 
    
- **Plano de discagem** de site : pode ser criado para um site inteiro, exceto para quaisquer usuários, grupos ou objetos de contato atribuídos a um plano de discagem de pool ou plano de discagem do usuário. Para definir um plano de discagem local, você deve especificar o local ao qual o plano de discagem é aplicado.
    
- **Plano de discagem global**: o plano de discagem padrão instalado com o produto. É possível editar o plano de discagem global, mas não exclui-lo. Esse plano de discagem se aplica a todos os Enterprise Voice, grupos e objetos de contato em sua implantação, a menos que você configure e atribua um plano de discagem com um escopo mais específico.
    
### <a name="planning-for-dial-plans"></a>Planejamento de planos de discagem

Para planejar um plano de discagem, siga estas etapas:
  
- Listar todas as localidades em que sua organização tem um escritório.
    
    A lista deve estar atualizada e concluída. Precisará ser revisada conforme a organização da empresa evolui. Em uma grande empresa multinacional com várias filiais pequenas, isso pode ser uma tarefa demorada.
    
- Identifique padrões de números válidos para cada site.
    
    A parte mais demorada do planejamento de seus planos de discagem é identificar os padrões de números válidos para cada local. Em alguns casos, será possível copiar as regras de normalização gravadas para um plano de discagem a outros planos de discagem, especialmente se os locais correspondentes estão dentro do mesmo país/região ou continente. Em outros casos, as pequenas alterações em números em um plano de discagem podem ser suficientes para usá-los em outros planos de discagem.
    
- Desenvolva um esquema de toda a organização para nomear planos de discagem.
    
    Adotar um esquema de nomeação padrão garante a consistência em toda a organização e facilita a manutenção e as atualizações.
    
- Decida se vários planos de discagem são necessários para um único local. 
    
    Se sua organização mantiver um único plano de discagem em vários locais, talvez você ainda precise criar um plano de discagem separado para usuários Enterprise Voice que estão migrando de um PBX (exchange de filial privada) e que precisam ter suas extensões existentes mantidas.
    
- Decida se os planos de discagem por usuário são necessários. Por exemplo, se você tiver usuários em um site de filial que estão registrados no site central ou se você tiver usuários registrados em um Aparelho de Filial Desavivável, você poderá considerar cenários de discagem especiais para esses usuários usando planos de discagem por usuário e regras de normalização. Para obter detalhes, [consulte Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Determine o escopo do plano de discagem (conforme descrito anteriormente neste tópico).
    
Para criar um plano de discagem, especifique valores nos campos a seguir, conforme necessário, usando Skype for Business Server Painel de Controle ou Skype for Business Server Shell de Gerenciamento.
  
#### <a name="name-and-simple-name"></a>Nome e o nome simples

Para planos de discagem de usuário, você deve especificar um nome descritivo que identifique os usuários, grupos ou objetos de contato aos quais o plano de discagem será atribuído. Para planos de discagem de site, o campo Nome é pré-preenchido com o nome do site e não pode ser alterado. Para planos de discagem de pool, o campo Nome é pré-preenchido com o gateway PSTN ou o FQDN (nome de domínio totalmente qualificado) do pool e não pode ser alterado.
  
O plano de discagem Nome Simples é pré-preenchido com uma cadeia de caracteres derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite que você crie uma convenção de nomenal mais descritiva para seus planos de discagem. O valor Nomesimple não pode estar vazio e deve ser exclusivo. Uma prática prática prática é desenvolver uma convenção de nomenis para toda a sua organização e, em seguida, usar essa convenção de forma consistente em todos os sites e usuários.
  
#### <a name="description"></a>Descrição

Recomendamos digitar o nome comum reconhecível da localização geográfica à qual se aplica o plano de discagem correspondente. Por exemplo, se o nome do plano de discagem for Londres.Contoso.com, a descrição recomendada seria Londres. 
  
#### <a name="dial-in-conferencing-region"></a>Região da conferência discada

Se você estiver implantando a conferência discada, precisará especificar uma região de conferência de discagem para associar os números de acesso da conferência discada com um plano de discagem. 
  
#### <a name="external-access-prefix"></a>Prefixo de acesso externo

Você pode especificar um prefixo de acesso externo de até quatro caracteres (#, , e 0-9) se os usuários precisarem discar um ou mais dígitos principais \* adicionais (por exemplo, 9) para obter uma linha externa.
  
> [!NOTE]
> Se você especificar um prefixo de acesso externo, não é necessário criar uma regra de normalização adicional para acomodar o prefixo. 
  
### <a name="normalization-rules"></a>Regras de normalização

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para o local nomeado. A mesma cadeia de caracteres de número pode ser interpretada e traduzida de forma diferente, dependendo da localidade da qual ela é discada. As regras de normalização são necessárias para o roteamento de chamada porque os usuários podem, e devem, usar vários formatos ao inserir números de telefone em suas listas de contatos.
  
A normalização dos números de telefone fornecidos pelo usuário fornece um formato consistente que facilita as seguintes tarefas:
  
- Corresponder um número discado ao SIP-URI do destinatário pretendido.
    
- Aplicar regras de autorização de discagem à parte de chamada.
    
Estes são alguns dos campos numéricos que as regras de normalização talvez precisem considerar:
  
- Plano de discagem
    
- Código do país
    
- Código de área
    
- Tamanho da extensão
    
- Prefixo do local
    
#### <a name="creating-normalization-rules"></a>Criando regras de normalização

As regras de normalização usam expressões regulares do .NET Framework para especificar padrões de correspondência numérica que o servidor usa para converter sequências de discagem para o formato E.164 para fins de pesquisa de número inverso. Você cria regras de normalização no Painel de Controle Skype for Business Server inserindo as expressões manualmente ou inserindo os dígitos ingressados e o comprimento das cadeias de caracteres de discagem a serem correspondida e deixando que o Painel de Controle Skype for Business Server gere a expressão regular correspondente para você. De qualquer forma, ao terminar, você pode inserir um número de teste para verificar se a regra de normalização funciona como esperado.
  
Para obter detalhes sobre como usar .NET Framework expressões regulares, consulte [".NET Framework Expressões Regulares"](/dotnet/standard/base-types/regular-expressions).
  
#### <a name="sample-normalization-rules"></a>Exemplos de regras de normalização
<a name="BKMK_SampleNormalizationRules"> </a>

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.
  
**Tabela 1. Regras de normalização usando expressões regulares do .NET Framework**

|**Nome da regra**|**Descrição**|**Padrão de número**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte extensões de 4 dígitos  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos  <br/> |^5(\d {4} )$  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos para números locais de Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/> |
|7digitcallingDallas  <br/> |Converte números de 7 dígitos para números locais de Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 é convertido em +19725550100  <br/> |
|10digitcallingUS  <br/> |Converte números de 10 dígitos nos Estados Unidos  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 é convertido em +12065550100  <br/> |
|LDCallingUS  <br/> |Converte números com prefixos de longa distância nos Estados Unidos  <br/> |^1(\d {10} )$  <br/> |+$1  <br/> |12145550100 é convertido em +2145550100  <br/> |
|IntlCallingUS  <br/> |Converte números com prefixos internacionais nos Estados Unidos  <br/> |^011(\d \* )$  <br/> |+$1  <br/> |01191445550100 é convertido em +91445550100  <br/> |
|RedmondOperator  <br/> |Converte 0 no operador de Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Redmond (222)  <br/> |^6222(\d {4} )$  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|NYSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Nova York (333)  <br/> |^6333(\d {4} )$  <br/> |+1202555$1  <br/> |63330100 é convertido em +12025550100  <br/> |
|DallasSitePrefix  <br/> |Converte números com o prefixo dentro da rede (6) e o código de área de Dallas (444)  <br/> |^6444(\d {4} )$  <br/> |+1972555$1  <br/> |64440100 é convertido em +19725550100  <br/> |
   
A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, baseado nas regras de normalização mostradas na tabela anterior.
  
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
> Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "extensão de 5-dígitos" e ainda ser válido. 
  
## <a name="voice-policies"></a>Políticas de voz

Skype for Business Server de voz definem o seguinte para cada usuário, site ou organização atribuído à política:
  
- Um conjunto de recursos de chamada que podem ser habilitados ou desabilitados para determinar Enterprise Voice funcionalidade disponível para os usuários.
    
- Um conjunto de registros de uso de PSTN (Rede telefônica comutada pública) que define quais tipos de chamadas são autorizadas. 
    
As etapas a seguir ajudarão você a planejar as políticas de voz necessárias para a implantação Enterprise Voice de voz:
  
- Determine como você configurará sua política de voz global (a política de voz padrão instalada com o produto). Essa política será aplicada a todos os Enterprise Voice usuários que não são atribuídos explicitamente a uma política no nível do site ou por usuário.
    
- Identifique as políticas de voz de nível de local que você possa precisar.
    
- Identifique as políticas de voz por usuário que você possa precisar.
    
- Decida quais recursos de chamada serão habilitados para cada política de voz.
    
- Determine quais registros de uso de PSTN configurar para cada política de voz.
    
### <a name="voice-policy-scope"></a>Escopo da política de voz

Escopo da política de voz determina o nível hierárquico no qual a política pode ser aplicada. Em Skype for Business Server, você pode configurar políticas de voz com os seguintes níveis de escopo (listados do mais específico para o mais geral).
  
- A **Política de voz de usuário** pode ser atribuída a usuários individuais, grupos ou objetos de contato. Essa á política de nível mais baixo. As políticas de voz de usuário podem ser implantadas a fim de habilitar recursos para determinados usuários ou grupos em um site, mas não para outros no mesmo site. Por exemplo, talvez você queira desabilitar a discagem de longa distância para alguns funcionários. Para o objetivo de atribuir uma política de voz, um objeto de contato é tratado como um usuário individual.
    
    > [!NOTE]
    > Recomendamos implantar uma política de voz de usuário para usuários de filial Enterprise Voice que estão registrados com a implantação do site central ou usuários registrados em um Aparelho de Filial Desavivável. 
  
- **Política de voz de site** se aplica a todo um site, exceto para quaisquer usuários, grupos ou objetos de contato que recebam uma política de voz de usuário. Para definir uma política de voz de site, você precisa especificar o site ao qual a política será aplicada. Se uma política de voz de usuário não tiver sido atribuída, a política de voz de site será usada.
    
- **Política de voz global** é a política de voz padrão, instalada com o produto. É possível editar a política de voz global a fim de atender às necessidades específicas de sua organização, mas não é possível renomear ou excluí-la. Essa política de voz se aplica a todos os Enterprise Voice usuários, grupos e objetos de contato em sua implantação, a menos que você configure e atribua uma política de voz com escopo mais específico. Se você quiser desabilitar totalmente essa política, certifique-se de que todos os sites e usuários tenham políticas personalizadas.
    
### <a name="call-features"></a>Recursos de chamada

É possível habilitar ou desabilitar os recursos de chamada a seguir para cada política de voz:
  
- **Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Habilitado por padrão.
    
- **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Habilitado por padrão.
    
- **Transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
- **Estacionamento de chamada** permite que os usuários estacionem chamadas e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
- **Toque simultâneo** permite que as chamadas recebidas toquem em um telefone adicional (por exemplo, um celular) ou outros dispositivos. Habilitado por padrão.
    
- **Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.
    
- **Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.
    
- **Substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamada para um usuário específico. Desabilitada por padrão.
    
- **O rastreamento de chamadas** mal-intencionadas permite que os usuários reportem chamadas mal-intencionadas usando o cliente Skype for Business e, em seguida, sinaliza essas chamadas nos registros de detalhes da chamada. Desabilitado por padrão.
    
- A **saída** de caixa postal impede que as chamadas são roteadas imediatamente para o sistema de caixa postal do telefone celular do usuário quando o toque simultâneo é configurado e o telefone está desligado, sem bateria ou fora do intervalo, e se baseia em um valor de timer. Esta configuração habilita e desabilita o temporizador e define o valor dele. Ele só pode ser configurado usando o Shell de Gerenciamento Skype for Business Server gerenciamento. Desabilitado por padrão.
    
- Os usos de **PSTN** de encaminhamento de chamadas e toque simultâneo permitem que os administradores especifiquem o mesmo uso PSTN da política de voz para encaminhamento de chamadas e toque simultâneo, restrinja o encaminhamento de chamadas e toque simultâneo para usuários internos do Skype for Business ou especifique um uso PSTN personalizado diferente do uso PSTN da política de voz. O padrão é usar o mesmo uso de PSTN que a política de voz para encaminhamento de chamadas e toque simultâneo.
    
### <a name="pstn-usage-records"></a>Registros de uso de PSTN

Cada política de voz deve ter um ou mais registros de uso de PSTN associados. Os usos de PSTN podem ser associados a uma política de voz somente para toque simultâneo e encaminhamento de chamadas. 
  
> [!NOTE]
> A ordem de uso de PSTN é fundamental, pois ao se comparar usuários a rotas, a funcionalidade de roteamento de saída compara as utilizações de PSTN do início ao fim. Se o primeiro uso corresponder à rota da chamada, essa rota será usada. Caso contrário, a funcionalidade de roteamento de saída analisa o próximo uso de PSTN na lista e continua até que uma correspondência seja encontrada. De fato, os usos de PSTN subsequentes fornecem um backup se o primeiro da lista não estiver disponível. 
  
## <a name="pstn-usage-records"></a>Registros de uso de PSTN

O planejamento dos registros de uso de PSTN consiste principalmente em listar todas as permissões de chamadas em uso na organização, desde o CEO até os funcionários temporários, os consultores e a equipe contingente. Esse processo também oferece uma oportunidade de reexaminar as permissões de chamadas existentes e revisá-las. Você pode criar registros de uso de PSTN somente para as permissões de chamada que se aplicam aos usuários previstos do Enterprise Voice, mas uma solução melhor e de longo alcance pode ser criar registros de PSTN para todas as permissões de chamadas, ainda que algumas delas não se apliquem no momento ao grupo de usuários que será habilitado para o Enterprise Voice. Se as permissões de chamada forem alteradas ou novos usuários com permissões de chamada diferentes forem adicionados, você já terá criado os registros de uso de PSTN necessários.
  
A tabela a seguir mostra um quadro típico de uso do PSTN.
  
**Registros de uso PSTN**

|**Atributo do telefone**|**Descrição**|
|:-----|:-----|
|Local  <br/> |Chamadas locais  <br/> |
|Long-Distance  <br/> |Chamadas interurbanas  <br/> |
|International  <br/> |Chamadas internacionais  <br/> |
|Délhi  <br/> |Funcionários de Délhi em tempo integral  <br/> |
|Redmond  <br/> |Funcionários de Redmond em tempo integral  <br/> |
|RedmondTemps  <br/> |Funcionários temporários de Redmond  <br/> |
|Richrich  <br/> |Funcionários de Zurique em tempo integral  <br/> |
   
Sozinhos, os registros de uso do PSTN não fazem nada. Para que funcionem, é necessário associá-los ao seguinte:
  
- Políticas de voz, que são atribuídas a usuários.
    
- Rotas, que são atribuídas a números de telefone.
    
## <a name="voice-routes"></a>Roteamento de voz

As rotas de chamada especificam como Skype for Business Server lida com chamadas de saída feitas por Enterprise Voice usuários. Quando um usuário disca um número, o Servidor front-end normaliza a cadeia de caracteres de discagem para o formato E.164, se necessário, e tenta match-lo com um URI SIP. Se o servidor não conseguir fazer a correspondência, aplicará a lógica de encaminhamento de chamadas realizadas com base no número. A etapa final na definição dessa lógica é a criação de uma rota de chamada nomeada separada para cada conjunto de números de telefone listados em cada plano de discagem.
  
Antes de definir as rotas de chamadas de saída, você deve concluir as seguintes etapas:
  
- Implantar um ou mais troncos.
    
- Criar planos de discagem conforme a necessidade para sites, indivíduos e objetos de Contato.
    
- Criar registros de uso de rede telefônica pública comutada (PSTN).
    
Além disso, para habilitar o roteamento de chamadas de saída, você deve criar e atribuir uma ou mais políticas de voz. Você pode fazer isso antes ou depois de definir as rotas das chamadas de saída.
  
Para cada rota, você deve especificar:
  
- Um nome pelo qual a rota possa ser facilmente identificada.
    
- Uma descrição opcional, caso apenas o nome não seja suficiente para descrevê-la.
    
- O padrão de correspondência da expressão regular que identifica os números de telefone de destino aos quais a rota será aplicada, junto com as exceções às quais o padrão de correspondência não será aplicado.
    
- Um ou mais troncos que você desejar atribuir à rota.
    
- Os registros de uso do PSTN que os usuários devem ter para fazer chamadas para números que correspondam à expressão regular do número de telefone de destino.
    
Você pode especificar rotas de chamada no painel Skype for Business Server Controle. Essas rotas de chamada preenchem a tabela de roteamento do servidor, que Skype for Business Server usa para rotear chamadas destinadas à PSTN.
  
### <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Skype for Business Server fornece flexibilidade na forma como as chamadas são roteados para a PSTN. Uma rota de voz especifica um conjunto de troncos ao PSTN que pode ser usado para uma chamada de voz específica. Um tronco associa um Servidor de Mediação e um número de porta a um gateway PSTN e um número de porta de escuta. Essa associação lógica permite que um Servidor de Mediação seja associado a vários gateways e tenha várias conexões com o mesmo gateway. Ao definir uma rota de chamada, especifique os troncos associados a essa rota, mas não especifique quais Servidores de Mediação estão associados à rota. Para criar troncos definindo as relações entre Servidores de Mediação e gateways PSTN, IP-PBXs e Controladores de Borda de Sessão (SBCs), use o Construtor de Topologias.
  
### <a name="least-cost-routing"></a>Roteamento de Custo Mínimo

A capacidade de especificar os troncos para os quais os diversos números são roteados permite determinar as rotas de menor custo e implementá-las adequadamente. A regra geral para selecionar troncos é escolher o tronco com o gateway mais próximo da localidade do número de destino para reduzir as tarifas de interurbano. Por exemplo, caso você esteja em Nova York telefonando para um número em Roma, a chamada seguiria pela rede IP até o tronco com o gateway no escritório de Roma e os custos seriam os de uma chamada local.
  
Para um exemplo de como o roteamento de custo mínimo poderia ser usado, considere o seguinte: a Fabrikam decide permitir que os usuários alemães façam chamadas para os números dos EUA usando o tronco norte-americano. A Fabrikam também deseja configurar o sistema para que todas as chamadas de usuários do Skype for Business Server para a Alemanha e países/regiões adjacentes terminem no tronco com o gateway na Alemanha. Este roteamento economizará dinheiro porque uma chamada da Alemanha para a Áustria, por exemplo, é mais barata do que uma chamada dos EUA para a Áustria.
  
### <a name="translating-outbound-dial-strings"></a>Como traduzir cadeias de caracteres de discagem de saída

Skype for Business Server exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso). Para troncos com gateways ou pbxs de filial privada que exigem números traduzidos em formatos de discagem local, o Skype for Business Server permite que você crie uma ou mais regras que ajudam a manipular o número chamado (ou seja, Solicitar URI) antes de roteá-lo para o tronco. Por exemplo, você pode escrever uma regra para remover +44 do início da cadeia de caracteres de discagem e subsituí-lo por 0144.
  
Com Skype for Business Server, é possível criar uma ou mais regras que ajudam a manipular o número de chamada antes de roteá-lo para o tronco.
  
Ao planejar seus troncos que associam pares de gateway:porta com pares de Servidor de Mediação:porta, pode ser útil agrupar troncos com requisitos de discagem local semelhantes e, portanto, reduzir o número de regras de conversão necessárias e o tempo necessário para escrevê-los.
  
### <a name="configuring-caller-id"></a>Como configurar o ID de chamador

Skype for Business Server fornece uma maneira de manipular a ID do chamador para chamadas de saída. Por exemplo, se uma organização quiser mascarar as extensões de discagem direta dos funcionários e substituí-las pelo número corporativo ou departmental genérico, um administrador poderá fazer isso usando o Painel de Controle do Skype for Business Server para suprimir a ID do chamador e substituí-la por uma ID de chamada alternativa especificada. Ao planejar sua lógica de roteamento, considere quais indivíduos, grupos, sites para os quais você deseja essa opção, talvez até mesmo para todos os funcionários.
  
> [!NOTE]
> Para chamadas que são roteadas novamente através do PSTN, o ID de chamador genérico será apresentado em vez do ID de chamador original. Isso pode fazer com que a chamada ignore configurações de Não Incomodar ou de privacidade que o receptor possa ter configurado. 
  
### <a name="additional-routing-logic"></a>Lógica de roteamento adicional

Ao criar rotas de chamadas de saída, você deve estar ciente dos seguintes fatores que podem afetar a lógica de roteamento:
  
- Onde uma chamada passa por uma fronteira federada, a parte do domínio do URI é usada para rotear a chamada até a empresa responsável por aplicar a lógica de roteamento de saída.
    
- Se a parte do domínio do URI de solicitação não contiver um domínio suportado para a empresa, o componente de roteamento de saída no servidor não processa a chamada.
    
- Se um usuário não estiver habilitado para Enterprise Voice, o servidor aplicará outra lógica de roteamento, conforme apropriado.
    
- Se uma chamada for roteada para um gateway que está completamente ocupado (todas as linhas do tronco estão ocupadas), o gateway rejeita a chamada e a lógica de roteamento de saída a redireciona para a próxima rota de menor custo. Considere isso cuidadosamente, porque um gateway dimensionado para um escritório pequeno no exterior (por exemplo, em Zurique) pode na verdade carregar um volume significativo de tráfego não-local para chamadas internacionais para a Suíça. Se o gateway não for dimensionado corretamente para esse tráfego adicional, as chamadas para a Suíça poderão ser roteadas por um gateway na Alemanha, resultando em tarifas maiores.
