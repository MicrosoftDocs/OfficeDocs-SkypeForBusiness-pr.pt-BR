---
title: Carregar dados de locatário e de criação no CQD (Painel de Qualidade de Chamada)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como carregar dados de locatário e de criação no CQD (Painel de Qualidade de Chamadas).
ms.openlocfilehash: d9559490aa990f3df800e0e9438810c63d153d3c
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789636"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Carregar dados de locatário e de criação no CQD (Painel de Qualidade de Chamada)


Para obter o máximo do CQD (Painel de Qualidade de Chamada), recomendamos que você carregue seu locatário e compile dados. Há dois tipos de arquivos de dados de locatário, [Criação](#upload-building-data-file) [e Ponto de Extremidade](#endpoint-data-file).

Você pode baixar um modelo de dados de locatário de [exemplo aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Para obter ajuda com o mapeamento de compilação, [leia Criar um mapa de construção para CQD](CQD-building-mapping.md).

No painel Relatórios de Resumo do CQD, selecione  Upload de Dados de Locatário **no menu** Configurações do CQD (um ícone de engrenagem na parte superior do CQD). A partir daqui, os administradores podem carregar as informações de criação e ponto de extremidade da organização, como mapeamento de endereços IP e informações geográficas, mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.

1. Abra o CQD (no centro de administração do Teams [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)ou em ), selecione o ícone de engrenagem no canto superior direito e escolha Carregar  Dados do Locatário na página Relatórios **de** Resumo.

   ![Captura de tela da caixa de diálogo que aparece enquanto os dados estão sendo carregados.](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, se esta for a primeira vez que você visita o CQD, você será solicitado a carregar dados de construção. Você pode selecionar **Carregar Agora para** navegar rapidamente até a página **Carregamento de Dados do** Locatário.

   ![Captura de tela da faixa que notifica um usuário para carregar dados de compilação.](media/qerguide-image-buildingdatauploadbanner.png)

3. Na página **Upload de Dados do** Locatário, selecione **Procurar** para escolher um arquivo de dados.

4. Depois de selecionar um arquivo de dados, especifique **a data de** início e, opcionalmente, especifique uma data de término.

5. Depois de **selecionar a data de** início, **selecione Carregar** para carregar o arquivo no CQD. <br><br>Antes que o arquivo seja carregado, ele é validado. Se a validação falhar, uma mensagem de erro será exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorre quando o número de colunas no arquivo de dados está incorreto.

   ![Exemplo de caixa de diálogo exibindo um erro de upload de dados de construção.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se nenhum erro ocorrer durante a validação, o upload do arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregado na tabela Meus uploads, que mostra a lista completa de todos os arquivos **carregados** para o locatário atual na parte inferior dessa página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já carregou um arquivo de construção e precisa adicionar sub-redes que podem ter sido perdidas ou excluídas, modifique o arquivo original adicionando as novas sub-redes, remova o arquivo atual e carregue novamente o arquivo recém-editado. Pode haver apenas um arquivo de dados de construção ativo no CQD. 


## <a name="upload-building-data-file"></a>Carregar arquivo de dados de compilação

O primeiro tipo de arquivo de dados de locatário no CQD é o **arquivo de** dados de criação. A coluna Sub-rede é derivada expandindo a coluna Network+NetworkRange e, em seguida, unindo a coluna Sub-rede à primeira sub-rede ou segunda sub-rede do registro de chamada para mostrar informações de construção, cidade, país ou região. O formato do arquivo de dados carregado deve atender aos seguintes critérios para passar na verificação de validação antes do upload:
  
- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O arquivo de dados não inclui uma linha de cabeçalho de tabela. Espera-se que a primeira linha do arquivo de dados sejam dados reais, não rótulos de cabeçalho como "Rede".

- Os tipos de dados no arquivo só podem ser String, Integer ou Boolean. Para o tipo de dados Integer, o valor deve ser um valor numérico. Os valores boolianos devem ser 0 ou 1.

- Se uma coluna usar o tipo de dados String, um campo de dados poderá estar vazio, mas ainda deverá ser separado por uma guia ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazio.

- Há um limite de 1.000.000 linhas expandida por arquivo de dados de locatário.

- Deve haver 15 colunas para cada linha, cada coluna deve ter o tipo de dados apropriado e as colunas devem estar na ordem listada na tabela a seguir (vírgula ou delimitada por tabulação):

  **Criando formato de arquivo de dados**
  
  | Nome da coluna        | Tipo de dados | Exemplo                   | Orientação              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Cadeia de caracteres    | 192.168.1.0               | Obrigatório              |
  | NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-SEA-1 | Obrigatório<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obrigatório              |
  | BuildingName       | Cadeia de caracteres    | SEATTLE-SEA-1             | Obrigatório<sup>1</sup>  |
  | OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional              |
  | BuildingType       | Cadeia de caracteres    | Encerramento de TI            | Opcional              |
  | BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional              |
  | Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado           |
  | ZipCode            | Cadeia de caracteres    | 98001                     | Recomendado           |
  | País            | Cadeia de caracteres    | NOS                        | Recomendado           |
  | Estado              | Cadeia de caracteres    | WA                        | Recomendado           |
  | Região             | Cadeia de caracteres    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obrigatório              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obrigatório              |
  | VPN                | Bool      | 0                         | Opcional              |

  <sup>1</sup> Embora não seja exigido pelo CQD, os modelos são configurados para exibir o nome de Criação e Rede.

  <sup>2</sup> Essa configuração pode ser usada para refletir se a sub-rede está ou não dentro da rede corporativa. Você pode personalizar o uso para outras finalidades.

  <sup>3</sup> Essa configuração pode ser usada para refletir se a rede usa ou não o Azure ExpressRoute. Você pode personalizar o uso para outras finalidades.  

  **Linha de exemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados quanto a intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar quaisquer sobreposições e corrigir o problema antes de carregar novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos incorretos de sub-redes para edifícios nos relatórios. Determinadas implementações de VPN não relatam com precisão as informações da sub-rede. 
>
> A coluna VPN é opcional e usará como padrão 0. Se o valor da coluna VPN for definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede. Use isso com moderação e somente para sub-redes VPN, pois a expansão total dessas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a criação de dados. Se a expansão da sub-rede resultar no limite de linha de expansão de 1.000.000 sendo excedido, o arquivo de construção não será aceito.


### <a name="supernetting"></a>Super-rede

Você pode usar a super-rede, normalmente chamada CIDR (Classless Inter-Domain Routing), em vez de definir cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço sobre vinhedo. Há suporte para a super-rede, mas não recomendamos usá-la.

Por exemplo, o prédio de marketing da Contoso é composto das sub-redes abaixo:

-   10.1.0.0/24 — primeiro andar
-   10.1.1.0/24 – segundo andar
-   10.1.2.0/24 – terceiro andar
-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço sobre vinhedo – neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0
-   Intervalo de Rede = 22

Aqui estão algumas coisas a serem consideradas antes de implementar a super-rede:

-   A super-rede só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits a 28 bits.

-   A super-rede leva menos tempo na frente, mas vem ao custo de reduzir a riqueza de seus dados. Digamos que haja um problema de qualidade envolvendo a sub-rede 10.1.2.0. Se você implementou a super-rede, não saberá onde na construção a sub-rede está localizada ou que tipo de rede ela é (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes para um prédio e carregado informações de local de piso, seria capaz de ver essa distinção.

-   É importante garantir que o endereço de sobre-vinhedo esteja correto e não esteja capturando sub-redes indesejadas.

-   É muito comum encontrar 192.168.0.0 em dados. Para muitas organizações, isso indica que o usuário está em casa. Para outros, esse é o esquema de endereços IP para um escritório satélite. Se sua organização tiver escritórios que usam essa configuração, não inclua-a no arquivo de construção porque é difícil distinguir entre redes internas e página inicial usando [sub-redes comuns](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todos os novos carregamentos de arquivo de dados de construção serão verificados quanto a intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar quaisquer sobreposições e corrigir o problema. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos incorretos de sub-redes para edifícios nos relatórios.

### <a name="vpn"></a>VPN

A qualidade dos dados de QoE (qualidade de experiência) que os clientes enviam para o Microsoft 365 ou Office 365 , que é de onde os dados CQD são originados, inclui um sinalizador vpn. O CQD verá isso como a primeira VPN e as segundas dimensões de VPN. No entanto, esse sinalizador depende do relatório de fornecedores de VPN para o Windows de que o adaptador de rede VPN registrado é um adaptador de Acesso Remoto. Nem todos os fornecedores de VPN registram corretamente os adaptadores de Acesso Remoto. Por isso, talvez você não consiga usar os filtros de consulta VPN internos. Use a coluna VPN discutida acima para marcar e identificar com precisão as sub-redes VPN. Também é uma boa prática rotular suas redes VPN para facilitar a identificação em seus relatórios. Abaixo estão dois exemplos de como rotular suas sub-redes VPN:

- Defina **um Nome de Rede** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando a VPN usando o nome da rede.](media/qerguide-image-vpnnetworkname.png)

- Defina **um Nome de Construção** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando a VPN usando o nome da compilação.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> As conexões VPN são conhecidas por identificar incorretamente o tipo de conexão de rede como com fio quando a conexão subjacente é sem fio. Ao examinar a qualidade em conexões VPN, você não pode supor que o tipo de conexão foi identificado com precisão.

## <a name="endpoint-data-file"></a>Arquivo de dados do ponto de extremidade

O outro tipo de arquivo de dados de locatário CQD é o **arquivo de dados do ponto** de extremidade. Os valores de coluna são usados na coluna Nome do Ponto de Extremidade do Cliente do registro de chamada ou na coluna Nome do Segundo Ponto de Extremidade do Cliente para mostrar informações de Tipo, Modelo ou Ponto de Extremidade. O formato do arquivo de dados carregado deve atender aos seguintes critérios para passar na verificação de validação antes do upload:

- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Espera-se que a primeira linha do arquivo de dados seja dados reais, não um rótulo de cabeçalho como "EndpointName".

- Todas as sete colunas usam apenas o tipo de dados String. O comprimento máximo permitido é de 64 caracteres.

- As entradas diferenciam maiúsculas de minúsculas; EndpointName **ABC123** será tratado como exclusivo de EndpointName **abc123**.

- Um campo de dados pode estar vazio, mas ainda deve ser separado por uma guia ou vírgula. Um campo de dados vazio apenas atribui um valor de cadeia de caracteres vazio.

- EndpointName deve ser exclusivo, caso contrário, o upload falhará. Se houver uma linha duplicada ou duas linhas que usam o mesmo EndpointName, o conflito causará uma junção incorreta.

- EndpointLabel1, EndpointLabel2 e EndpointLabel3 são rótulos personalizáveis. Eles podem ser cadeias de caracteres vazias ou valores como "Laptop designado pelo Departamento de TI 2018" ou "Marca de Ativo 5678".

- Deve haver sete colunas para cada linha e as colunas devem estar na seguinte ordem:

  **Ordem do campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Linha de exemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Atualizar um arquivo de construção

Durante a coleta de informações de criação e sub-rede, os administradores geralmente carregarão o arquivo de construção em várias iterações ao longo do tempo, adicionando novas sub-redes e suas informações de compilação à medida que ele se tornar disponível. Quando isso ocorrer, você precisará carregar novamente o arquivo de construção. Esse processo é como o carregamento inicial, conforme descrito na seção anterior, com algumas exceções, conforme mostrado na seção a seguir.

> [!Important]
> Somente um arquivo de construção pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

## <a name="add-net-new-subnets"></a>Adicionar novas sub-redes net

Há ocasiões em que você precisará adicionar novas sub-redes líquidas ao CQD que não eram originalmente parte de sua topologia de rede. Para adicionar novas sub-redes net, faça o seguinte na página Upload de Dados **do Locatário** no CQD:

1.  Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1.  Remova o arquivo atual no CQD.

1.  Edite o arquivo de construção original e forneça uma data de término que ocorre pelo menos um dia antes da aquisição das novas sub-redes líquidas.

1.  Acrescente as novas sub-redes net ao arquivo de construção original.

1.  Carregue o arquivo de construção recém-modificado e defina a data de início para um dia após o término do arquivo de construção anterior.

## <a name="add-missing-subnets"></a>Adicionar sub-redes ausentes

Depois de carregar informações de criação para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre será o caso; normalmente, algumas sub-redes são perdidas. Para localizar essas redes ausentes, examine o **Relatório de Sub-rede** ausente na **página Relatórios de** Qualidade da Experiência no CQD. Isso apresenta todas as sub-redes com 10 ou mais fluxos de áudio que não estão definidos no arquivo de dados de construção e estão sendo marcados como externos. Verifique se não há redes gerenciadas nesta lista. Se as sub-redes estiverem ausentes, use o procedimento a seguir para atualizar o arquivo de dados de construção original e carregá-lo novamente no CQD.

1. Vá para a **página Upload de Dados do** Locatário no CQD.

1. Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1. Remova o arquivo atual no CQD.

1. Acrescente as novas sub-redes ao arquivo original.

1. Carregue o arquivo de construção. Defina a data de início como pelo menos oito meses antes para que o CQD processe dados históricos.


> [!IMPORTANT]
> Você precisará adicionar sua ID de locatário como um filtro de consulta para a **segunda ID** de locatário a esse relatório para filtrar o relatório para exibir apenas os dados de locatário da sua organização. Caso contrário, o relatório mostrará sub-redes federadas.

> [!NOTE] 
> Certifique-se de ajustar o filtro de relatório ano mês para o mês atual. Selecione **Editar** e ajuste o filtro **de relatório ano** mês para salvar o novo mês padrão.


## <a name="related-topics"></a>Tópicos relacionados

[Criar um mapa de construção para CQD](CQD-building-mapping.md)

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
