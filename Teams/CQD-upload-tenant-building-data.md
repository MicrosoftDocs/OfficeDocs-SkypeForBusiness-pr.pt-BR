---
title: Carregar o locatário e compilar dados no painel de qualidade de chamada (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como carregar locatários e compilar dados no painel de qualidade de chamada (CQD).
ms.openlocfilehash: 37499cf2715a3cabb05ab5039a19190190253b07
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897831"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Carregar o locatário e compilar dados no painel de qualidade de chamada (CQD)


Para aproveitar ao máximo o painel de qualidade da chamada (CQD), recomendamos que você carregue seu locatário e dados de construção. Há dois tipos de arquivos de dados locatários, [construção](#upload-building-data-file) e [ponto de extremidade](#endpoint-data-file).

Você pode baixar um modelo de dados de locatário de exemplo [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Para obter ajuda com o mapeamento de construção, leia [criar um mapa de construção para CQD](CQD-building-mapping.md).

No painel relatórios de resumo do CQD, selecione **carregar dados do locatário** no menu **configurações** do CQD (um ícone de engrenagem na parte superior da CQD). Aqui, os administradores podem carregar a construção e as informações de ponto de extremidade da organização, como o mapeamento de endereços IP e informações geográficas, o mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.

1. Abra o CQD (no centro de administração do teams ou em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ) e, em seguida, selecione o ícone de engrenagem no canto superior direito e escolha **carregamento de dados do locatário** na página relatórios de **Resumo** .

   ![Captura de tela da caixa de diálogo que aparece enquanto os dados são carregados](media/qerguide-image-tenantdataupload.png)
    
2. Ou, se esta for a primeira vez que visitar CQD, você será solicitado a carregar os dados de construção. Você pode selecionar **carregar agora** para navegar rapidamente até a página de **carregamento de dados do locatário** .

   ![Captura de tela da faixa que notifica um usuário para carregar dados de construção](media/qerguide-image-buildingdatauploadbanner.png)

3. Na página **carregamento de dados do locatário** , selecione **procurar** para escolher um arquivo de dados.

4. Depois de selecionar um arquivo de dados, especifique **data de início** e, opcionalmente, especifique uma data de término.

5. Depois de selecionar **data de início**, selecione **carregar** para carregar o arquivo para CQD. <br><br>Antes de o arquivo ser carregado, ele é validado. Se a validação falhar, uma mensagem de erro será exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorre quando o número de colunas no arquivo de dados está incorreto.

   ![Exemplo de caixa de diálogo exibindo um erro de carregamento de dados de construção](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se não ocorrerem erros durante a validação, o carregamento do arquivo será bem-sucedido. Em seguida, você pode ver o arquivo de dados carregado na tabela **My uploads** , que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já carregou um arquivo de construção e precisa adicionar sub-redes que possam ter sido perdidos ou excluídos, modifique o arquivo original adicionando as novas sub-redes, remova o arquivo atual e carregue novamente o arquivo recentemente editado. Pode haver apenas um arquivo de criação de dados ativo no CQD. 


## <a name="upload-building-data-file"></a>Carregar arquivo de construção de dados

O primeiro tipo de arquivo de dados locatário no CQD é o arquivo de dados de **construção** . A coluna de sub-rede é derivada expandindo a coluna Network + NetworkRange e, em seguida, ingressando na coluna subnet na primeira sub-rede ou segunda coluna do registro de chamada para mostrar as informações de construção, cidade, país ou região. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes do carregamento:
  
- O arquivo deve ser um arquivo. TSV (as colunas são separadas por uma TABULAção) ou um arquivo. csv (as colunas são separadas por uma vírgula).

- O arquivo de dados não inclui uma linha de cabeçalho de tabela. Espera-se que a primeira linha do arquivo de dados seja dados reais, e não rótulos de cabeçalho como "rede".

- Os tipos de dados no arquivo só podem ser String, Integer ou Boolean. Para o tipo de dados inteiro, o valor deve ser um valor numérico. Os valores Boolianos devem ser 0 ou 1.

- Se uma coluna usa o tipo de dados de cadeia de caracteres, um campo de dados pode estar vazio, mas ainda deve ser separado por uma Tabulação ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazia.

- Deve haver 14 colunas para cada linha, cada coluna deve ter o tipo de dados apropriado, e as colunas devem estar na ordem listada na tabela a seguir (vírgula ou delimitada por tabulação):

  **Criando um formato de arquivo de dados**
  
  | Nome da coluna        | Tipo de dados | Exemplo                   | Orientação              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Cadeia de caracteres    | 192.168.1.0               | Obrigatório              |
  | NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-SEA-1 | Obrigatório<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obrigatório              |
  | BuildingName       | Cadeia de caracteres    | SEATTLE-SEA-1             | Obrigatório<sup>1</sup>  |
  | Propriedadetype      | Cadeia de caracteres    | Contoso.com                   | Opcional              |
  | Buildingtype       | Cadeia de caracteres    | Terminações            | Opcional              |
  | BuildingOfficeType | Cadeia de caracteres    | Engineer               | Opcional              |
  | Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado           |
  | ZipCode            | Cadeia de caracteres    | 98001                     | Recomendado           |
  | País            | Cadeia de caracteres    | Junte                        | Recomendado           |
  | Estado              | Cadeia de caracteres    | WA                        | Recomendado           |
  | Região             | Cadeia de caracteres    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obrigatório              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obrigatório              |
  | VPN                | Bool      | 0                         | Opcional              |

  <sup>1</sup> embora não seja exigido pelo CQD, os modelos são configurados para exibir o prédio e o nome da rede.

  <sup>2</sup> essa configuração pode ser usada para refletir se a sub-rede está ou não dentro da rede corporativa. Você pode personalizar o uso para outras finalidades.

  <sup>3</sup> essa configuração pode ser usada para refletir se a rede usa o Azure ExpressRoute. Você pode personalizar o uso para outras finalidades.  

  **Linha de amostra:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema antes de carregá-lo novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para prédios nos relatórios. Algumas implementações de VPN não reportam precisamente as informações de sub-rede. 
>
> A coluna VPN é opcional e será definida como padrão 0. Se o valor da coluna VPN estiver definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede.  Use isso de maneira moderada e somente para sub-redes VPN, já que expandir totalmente essas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a construção de dados.


### <a name="supernetting"></a>Combinação de sub-redes

Você pode usar a combinação de redes, comumente chamada de roteamento Inter-Domain sem classe (CIDR), no lugar da definição de cada sub-rede. Um *Supernet* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sub-rede. Há suporte para a combinação de sub-redes, mas não recomendamos usá-la.

Por exemplo, a compilação de marketing da Contoso é composta pelas subredes abaixo:

-   10.1.0.0/24 — primeiro andar
-   10.1.1.0/24 — segundo andar
-   10.1.2.0/24 – terceiro andar
-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sub-rede e, neste exemplo, 10.1.0.0/22.

-   Network = 10.1.0.0
-   Intervalo de rede = 22

Aqui estão algumas coisas a serem consideradas antes de implementar a combinação de sub-redes:

-   A combinação de redes só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits a 28 bits.

-   A combinação de sub-redes leva menos tempo, mas tem o custo de reduzir a riqueza dos seus dados. Digamos que há um problema de qualidade envolvendo a subnet 10.1.2.0. Se você implementou a combinação de redes, não sabe onde está localizado o que está criando a sub-rede ou qual é o tipo da rede (por exemplo, um laboratório). Se você definiu todas as sub-redes para criar e carregar as informações de localização de chão, você poderá ver essa distinção.

-   É importante certificar-se de que o endereço de sub-rede está correto e não está capturando sub-redes não desejadas.

-   É muito comum localizar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outros, é o esquema de endereço IP para um escritório de satélite. Se a sua organização tem escritórios que usam essa configuração, não a inclua em seu arquivo de construção porque é difícil distinguir entre redes domésticas e internas usando [sub-redes comuns](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet. Todos os novos carregamentos de arquivos de dados de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para edifícios nos relatórios.

### <a name="vpn"></a>VPN

Os dados de qualidade da experiência (QoE) que os clientes enviam para o Microsoft 365 ou o Office 365, onde os dados do CQD são originados a partir de — inclui um sinalizador de VPN. O CQD o verá como a primeira e a segunda dimensões de VPN e VPN. No entanto, esse sinalizador depende dos relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN está cadastrado é um adaptador de acesso remoto. Nem todos os fornecedores de VPN registram corretamente adaptadores de acesso remoto. Por isso, talvez você não possa usar os filtros de consulta VPN internos. Use a coluna VPN abordada acima para marcar e identificar com precisão as sub-redes VPN. Também é uma boa prática identificar suas redes VPN para facilitar a identificação em seus relatórios. Veja a seguir dois exemplos de como rotular suas sub-redes VPN:

- Defina um **nome de rede** digitando "VPN" nesse campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da rede](media/qerguide-image-vpnnetworkname.png)

- Defina um **nome de edifício** inserindo "VPN" nesse campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da construção](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> As conexões VPN receberam a identificação do tipo de conexão de rede como Wired quando a conexão subjacente é sem fio. Ao examinar a qualidade em conexões VPN, você não pode presumir que o tipo de conexão foi identificado de forma precisa.

## <a name="endpoint-data-file"></a>Arquivo de dados de ponto de extremidade

O outro tipo de arquivo de dados locatário CQD é o arquivo de dados do **ponto de extremidade** . Os valores de coluna são usados na coluna nome do ponto de extremidade do primeiro cliente ou segundo nome do ponto de extremidade do cliente para mostrar informações sobre tipo, modelo ou marca de ponto de extremidade. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes do carregamento:

- O arquivo deve ser um arquivo. TSV (as colunas são separadas por uma TABULAção) ou um arquivo. csv (as colunas são separadas por uma vírgula).

- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Espera-se que a primeira linha do arquivo de dados seja real, não um rótulo de cabeçalho como "EndpointName".

- Todas as seis colunas usam somente o tipo de dados de cadeia de caracteres. O comprimento máximo permitido é de 64 caracteres.

- Um campo de dados pode estar vazio, mas ainda deve ser separado por uma Tabulação ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazia.

- EndpointName deve ser exclusivo; caso contrário, o carregamento falhará. Se houver uma linha duplicada ou duas linhas com o mesmo ponto de extremidadename, o conflito causará a junção incorreta.

- EndpointLabel1, EndpointLabel2 e EndpointLabel3 são rótulos personalizáveis. Elas podem ser cadeias de caracteres ou valores vazios, como o "departamento de ti designado 2018 laptop" ou "marca do ativo 5678".

- Deve haver seis colunas para cada linha, e as colunas devem estar na seguinte ordem:

  **Ordem dos campos:**

  EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Linha de amostra:**

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  


## <a name="update-a-building-file"></a>Atualizar um arquivo de construção

Durante a coleta de informações de construção e de sub-rede, os administradores geralmente carregam o arquivo de construção em várias iterações ao longo do tempo, adicionando novas sub-redes e suas informações de construção à medida que se tornam disponíveis. Quando isso ocorrer, será necessário carregar novamente o seu arquivo de construção. Esse processo é como o upload inicial, conforme descrito na seção anterior, com algumas exceções, conforme observado na seção a seguir.

> [!Important]
> Somente um arquivo de construção pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

## <a name="add-net-new-subnets"></a>Adicionar nova sub-rede

Há ocasiões em que você precisará adicionar novas sub-redes ao CQD que não faziam parte da topologia de rede. Para adicionar novas sub-redes, faça o seguinte na página de **carregamento de dados do locatário** no CQD:

1.  Baixe o arquivo original, caso ainda não tenha uma cópia atualizada.

1.  Remova o arquivo atual no CQD.

1.  Edite o arquivo de construção original e forneça uma data de término que ocorra pelo menos um dia antes da aquisição da nova sub-rede.

1.  Acrescente novas sub-redes ao arquivo de construção original.

1.  Carregue o arquivo de criação recém modificado e defina a data de início para um dia após o término do arquivo de construção anterior.

## <a name="add-missing-subnets"></a>Adicionar sub-redes ausentes

Depois de carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre é o caso; Geralmente, algumas sub-redes são perdidas. Para encontrar essas redes ausentes, examine o **relatório de sub-rede ausente** na página de **relatórios de qualidade da experiência** no CQD. Isso apresenta todas as sub-redes com 10 ou mais fluxos de áudio que não são definidos no arquivo de dados de construção e são marcados como externos. Certifique-se de que não há redes gerenciadas nesta lista. Se as sub-redes estiverem ausentes, use o procedimento a seguir para atualizar o arquivo de dados de construção original e carregá-lo novamente no CQD.

1. Vá para a página de **carregamento de dados do locatário** no CQD.

1. Baixe o arquivo original, caso ainda não tenha uma cópia atualizada.

1. Remova o arquivo atual no CQD.

1. Acrescentar as novas sub-redes ao arquivo original.

1. Carregue o arquivo de construção. Certifique-se de definir a data de início com pelo menos oito meses antes de que o CQD processe dados históricos.


> [!IMPORTANT]
> Você precisará adicionar sua ID de locatário como um filtro de consulta para a **segunda ID de locatário** a esse relatório para filtrar o relatório e exibir somente os dados locatários da sua organização. Caso contrário, o relatório mostrará sub-redes federadas.

> [!NOTE] 
> Certifique-se de ajustar o filtro de relatório de ano do mês para o mês atual. Selecione **Editar**e ajuste o filtro relatório de **ano do mês** para salvar o novo mês padrão.


## <a name="related-topics"></a>Tópicos relacionados

[Criar um mapa de construção para CQD](CQD-building-mapping.md)

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
