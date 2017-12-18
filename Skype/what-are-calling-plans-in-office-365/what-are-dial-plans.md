---
title: "Quais são os planos de discagem?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
description: "Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your company.  "
---

# Quais são os planos de discagem?

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Um plano de discagem é um conjunto nomeado de regras de normalização que converte os números de telefone discados por um usuário em um formato alternativo (normalmente E.164) para fins de autorização e roteamento de chamadas.
  
Um plano de discagem consiste em uma ou mais regras de normalização que definem como expressos em vários formatos de números de telefone são convertidos em um formato alternativo. A mesma sequência de discagem pode ser interpretada e traduzida de forma diferente em diferentes planos de discagem, portanto, dependendo de qual plano de discagem é atribuído a um determinado usuário, a mesma discado número pode ser traduzido e roteado de forma diferente.
  
Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar planos de discagem de locatário.
  
## Escopo do plano de discagem do locatário

Escopo de um plano de discagem determina o nível hierárquico no qual o plano de discagem pode ser aplicado. Os escopos são diferentes em um Skype for Business Server 2015 local implantação. Os clientes obtêm o plano de discagem apropriado por meio de provisionamento configurações que são fornecidas automaticamente quando os usuários fazem logon para Skype for Business Online. Como administrador, você pode gerenciar e atribuir níveis de escopo de plano de discagem usando o PowerShell remoto.
  
No Skype for Business Online, há dois tipos de planos de discagem - serviço com escopo e locatário (que é para a sua organização) com escopo. Um plano de discagem de serviço com escopo definido para cada país/região onde o sistema de telefone do Office 365 está disponível. Cada usuário é automaticamente atribuído o plano de discagem do país/região de serviço que coincida com o local de uso do Office 365 atribuídas ao usuário. Não é possível alterar o plano de discagem do país/região de serviço, mas você pode criar planos de discagem de locatário escopo, que aumentar o plano de discagem do país/região de serviço. Como os clientes são provisionados, eles obtenham um "plano de discagem eficaz", que é uma combinação de plano de discagem do país/região do serviço e o plano de discagem de locatário adequadamente com escopo. Portanto, não é necessário definir todas as regras de normalização em planos de discagem do locatário como eles podem já existem no plano de discagem do país/região do serviço.
  
Os planos de discagem do locatário podem ser divididos em dois escopos: escopo do locatário ou do usuário. Se um locatário definir e atribuir um plano de discagem de usuário com escopo, então esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem de usuário atribuído. Se um locatário definir um plano de discagem de locatário com escopo, mas não atribuir um plano de discagem de usuário com escopo, então esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem do locatário.
  
A seguir é apresentado o modelo de herança de planos de discagem no Skype for Business Online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
A seguir são apresentados planos de discagem efetivos possíveis:
  
 **País de serviço** Se nenhum plano de discagem de locatário com escopo definido e nenhum plano de discagem do usuário com escopo de locatário é atribuído ao usuário provisionado, o usuário receberá um plano de discagem eficaz mapeado para o país de serviço associado ao seu local de uso do Office 365.
  
 **Locatário Global - país de serviço** Se um plano de discagem de usuário de Inquilino é definido, mas não atribuído a um usuário, o usuário provisionado receberá um plano de discagem eficiente consiste em um plano de discagem de locatário mescladas e o plano de discagem do país/região de serviço associado ao seu local de uso do Office 365.
  
 **Usuário de locatário - país de serviço** Se um plano de discagem de usuário de Inquilino é definido e atribuído a um usuário, o usuário provisionado receberá um plano de discagem eficaz consiste o plano de discagem de usuário de Inquilino mescladas e o plano de discagem do país/região de serviço associado ao seu local de uso do Office 365.
  
Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seu locatário planos de discagem.
  
## Planejamento de planos de discagem de locatário

Para planejar os planos de discagem personalizado, siga estas etapas:
  
- **Etapa 1** Decida se um personalizado discar plano é necessária para aprimorar o usuário experiência de discagem. Normalmente, a necessidade de um seria dar suporte a discagem não e. 164, como extensões ou abreviado discagem nacional.
    
- **Etapa 2** Determine se o locatário global ou planos de discagem do usuário com escopo de locatário são necessários ou ambos. Planos de discagem do usuário com escopo são necessários se os usuários têm requisitos de discagem locais diferentes.
    
- **Etapa 3** Identifique padrões de número válido para cada plano de discagem necessário. Somente os padrões de número que não são definidos nos planos de discagem de país de nível de serviço são necessários.
    
- **Etapa 4** Desenvolva um esquema em toda a organização para nomear os planos de discagem. A adoção de um esquema de nomenclatura padrão assegura a consistência em toda a organização e facilita a manutenção e as atualizações.
    
O [Fasttrackhttp](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) tem recursos adicionais e planos de discagem de parceiros que podem ajudá-lo com a implementação do locatário.
  
## Criação de novo plano de discagem de locatário

Quando você criar um novo plano de discagem, insira as informações necessárias.
  
### Nome e nome simples

Para planos de discagem do usuário, você deverá especificar um nome descritivo que identifica aos usuários o plano de discagem será atribuído. O plano de discagem nome simples é pré-populado com uma cadeia de caracteres que é derivada do nome do plano de discagem. O campo de nome simples é editável, que permite que você crie uma convenção de nomenclatura mais descritiva para seus planos de discagem. O valor de nome simples não pode ser vazio e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para sua organização inteira e, em seguida, usar essa convenção de maneira uniforme em todos os sites e usuários.
  
### Descrição

Recomendamos que você digite o nome comum e reconhecível da localização geográfica ou grupo de usuários para os quais o plano de discagem correspondente se aplica.
  
### Prefixo de acesso externo

> [!CAUTION]
> O prefixo de acesso externo não tem suporte atualmente 
  
É possível especificar um prefixo de acesso externo de até quatro caracteres (#, * e 0-9) se os usuários precisam discar um ou mais dígitos adicionais (por exemplo, 9) para obter uma linha externa.
  
> [!NOTE]
> Se você especificar um prefixo de acesso externo, não será necessário criar uma regra de normalização adicional para acomodar o prefixo. 
  
Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seu locatário planos de discagem.
  
## Regras de normalização

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser convertidos. A mesma sequência de números pode ser interpretada e convertida de modos diferentes dependendo do local de onde for discada. As regras de normalização podem ser necessárias, se os usuários precisarem discar números internos ou externos abreviados.
  
Uma ou mais regras de normalização devem ser atribuídas ao plano de discagem. Regras de normalização são comparadas de cima para baixo, para que a ordem em que aparecem em um plano de discagem de locatário é importante. Por exemplo, se um plano de discagem de locatário tiver 10 regras de normalização, a lógica de correspondência número discada será tentado começando com a primeira regra de normalização, se não houver uma correspondência, em seguida, o segundo e assim por diante. Se uma correspondência for feita, essa regra é usada e não há nenhum esforço para corresponder ao quaisquer outras regras que são definidas. Pode haver um máximo de 25 regras de normalização em um plano de discagem de locatário determinado.
  
### Determinação de regras de normalização necessárias

Como qualquer plano de discagem de locatário é combinado efetivamente com um plano de discagem do país de serviço de um usuário específico, é provável que as regras de normalização do plano de discagem do país do serviço sejam avaliadas para determinar quais regras de normalização do plano de discagem do locatário são necessárias. O cmdlet **Get-CsEffectiveTenantDialPlan** pode ser usado para essa finalidade. O cmdlet usa a identidade de um usuário como parâmetro de entrada e retorna todas as regras de normalização aplicáveis ao usuário.
  
### Criação de regras de normalização

As regras de normalização usam as expressões regulares do .NET Framework para especificar os padrões de correspondência numérica que o servidor usa para converter as sequências de caracteres de discagem para o formato E.164 com a finalidade de executar uma consulta reversa de número. As regras de normalização podem ser criadas especificando a expressão regular para a correspondência e a conversão a ser feita quando uma correspondência é encontrada. Ao concluir, você pode digitar um número de teste para verificar se a regra de normalização funciona como o esperado.
  
Para obter detalhes sobre como usar expressões regulares do .NET Framework, consulte [Expressões regulares do .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar normalização regras para seu locatário planos de discagem.
  
### Regras de normalização de exemplo

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.
  
 **Regras de normalização usando expressões regulares do .NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome da regra** <br/> |**Descrição** <br/> |**Padrão de número** <br/> |**Conversão** <br/> |**Exemplo** <br/> |
|4digitExtension  <br/> |Converte extensões de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos para números locais Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/> |
|RedmondOperator  <br/> |Converte 0 para o Operador Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo (6) na rede e o código de local do Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|5digitRange  <br/> |Converte extensões de 5 dígitos iniciando com o intervalo de dígitos de 3 a 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 é convertido em +14255554567  <br/> |
|PrefixAdded  <br/> |Adiciona um prefixo de país na frente de um número de 9 dígitos com restrições no primeiro e terceiro dígitos.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 é convertido em 14255554567  <br/> |
|NoTranslation  <br/> |Corresponde 5 dígitos, mas não faz a conversão.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 é convertido em 34567  <br/> |
   
 **Plano de discagem de Redmond com base nas regras de normalização mostradas acima.**
  
A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, com base nas regras de normalização mostradas na tabela anterior.
  
||
|:-----|
|**Plano de discagem de Redmond** <br/> |
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|RedmondSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma opção. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido. 
  
## Tópicos Relacionados

[Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

