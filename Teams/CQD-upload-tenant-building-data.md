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
description: Saiba como carregar dados de locatário e de criação no CQD (Painel de Qualidade de Chamada).
ms.openlocfilehash: d999098a2d920c8709ae1878ac94648451c00f0b
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163221"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Carregar dados de locatário e de criação no CQD (Painel de Qualidade de Chamada)


Para aproveitar ao máximo o CQD (Painel de Qualidade de Chamada), recomendamos carregar seus dados de locatário e de criação. Há dois tipos de arquivos de dados de locatário, [Building](#upload-building-data-file) e [Endpoint](#endpoint-data-file).

Você pode baixar um modelo de dados de locatário [de exemplo aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Para obter ajuda com o mapeamento de construção, leia [Criar um mapa de construção para CQD](CQD-building-mapping.md).

No painel Relatórios de Resumo do CQD, selecione **Carregar Dados do Locatário** no menu **Configurações** do CQD (um ícone de engrenagem na parte superior do CQD). A partir daqui, os administradores podem carregar as informações de construção e ponto de extremidade de sua organização, como mapeamento de endereços IP e informações geográficas, mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.

1. Abra o CQD (no centro de administração do Teams ou no [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), selecione o ícone de engrenagem no canto superior direito e escolha **Carregar Dados do Locatário** na página **Relatórios de Resumo** .

   ![Captura de tela da caixa de diálogo que aparece enquanto os dados estão sendo carregados.](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, se essa for sua primeira vez visitando o CQD, você será solicitado a carregar dados de construção. Você pode selecionar **Carregar Agora** para navegar rapidamente até a página **Carregar Dados do Locatário** .

   ![Captura de tela do banner que notifica um usuário a carregar dados de construção.](media/qerguide-image-buildingdatauploadbanner.png)

3. Na página **Carregar Dados do Locatário** , selecione **Procurar** para escolher um arquivo de dados.

4. Depois de selecionar um arquivo de dados, especifique **a data de início** e, opcionalmente, especifique uma data de término.

5. Depois de selecionar **a data de início**, selecione **Carregar** para carregar o arquivo no CQD. <br><br>Antes que o arquivo seja carregado, ele é validado. Se a validação falhar, uma mensagem de erro será exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro ocorrendo quando o número de colunas no arquivo de dados está incorreto.

   ![Exemplo da caixa de diálogo que exibe um erro de carregamento de dados de construção.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se nenhum erro ocorrer durante a validação, o upload do arquivo será bem-sucedido. Em seguida, você pode ver o arquivo de dados carregado na tabela **Meus uploads** , que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior dessa página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já carregou um arquivo de construção e precisa adicionar sub-redes que podem ter sido perdidas ou excluídas, modifique o arquivo original adicionando as novas sub-redes, remova o arquivo atual e carregue novamente o arquivo recém-editado. Só pode haver um arquivo de dados de construção ativo no CQD. 


## <a name="upload-building-data-file"></a>Carregar arquivo de dados de construção

O primeiro tipo de arquivo de dados de locatário no CQD é o arquivo **de dados Building** . A coluna Sub-rede é derivada pela expansão da coluna Network+NetworkRange e, em seguida, a junção da coluna Sub-rede à primeira sub-rede ou segunda sub-rede do registro de chamada para mostrar informações de Construção, Cidade, País ou Região. O formato do arquivo de dados carregado deve atender aos seguintes critérios para passar a verificação de validação antes de carregar:
  
- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O arquivo de dados não inclui uma linha de cabeçalho de tabela. Espera-se que a primeira linha do arquivo de dados seja dados reais, não rótulos de cabeçalho como "Rede".

- Os tipos de dados no arquivo só podem ser String, Integer ou Boolean. Para o tipo de dados Inteiro, o valor deve ser um valor numérico. Os valores boolianos devem ser 0 ou 1.

- Se uma coluna usa o tipo de dados String, um campo de dados pode estar vazio, mas ainda deve ser separado por uma guia ou vírgula. Um campo de dados vazio atribui apenas um valor de cadeia de caracteres vazio.

- Há um limite de linha expandido de 1.000.000 por arquivo de dados de locatário.

- Deve haver 15 colunas para cada linha, cada coluna deve ter o tipo de dados apropriado e as colunas devem estar na ordem listada na tabela a seguir (vírgula ou guia delimitada):

  **Formatar o formato de arquivo de dados**
  
  | Nome da coluna        | Tipo de dados | Exemplo                   | Orientação              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Cadeia de caracteres    | 192.168.1.0               | Obrigatório              |
  | NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-SEA-1 | Necessário<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obrigatório              |
  | BuildingName       | Cadeia de caracteres    | SEATTLE-SEA-1             | Necessário<sup>1</sup>  |
  | OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional<sup>4</sup>  |
  | BuildingType       | Cadeia de caracteres    | Término de TI            | Opcional<sup>4</sup>  |
  | BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional<sup>4</sup>  |
  | Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado           |
  | ZipCode            | Cadeia de caracteres    | 98001                     | Recomendado           |
  | País            | Cadeia de caracteres    | Nos                        | Recomendado           |
  | Estado              | Cadeia de caracteres    | Wa                        | Recomendado           |
  | Região             | Cadeia de caracteres    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obrigatório              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obrigatório              |
  | VPN                | Bool      | 0                         | Opcional              |

  <sup>1</sup> Embora não seja necessário pelo CQD, os modelos são configurados para exibir o nome de criação e rede.

  <sup>2</sup> Essa configuração pode ser usada para refletir se a sub-rede está ou não dentro da rede corporativa. Você pode personalizar o uso para outras finalidades.

  <sup>3</sup> Essa configuração pode ser usada para refletir se a rede usa ou não o Azure ExpressRoute. Você pode personalizar o uso para outras finalidades.  
  
  <sup>4</sup> Embora essas colunas opcionais sejam nomeadas para sugerir quais valores você pode querer preenchê-las, você pode personalizar o uso para outras finalidades. por exemplo: Prioridade de rede – `Tier 1, Tier 2, Tier 3` 

  **Linha de exemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos uploads de construção serão verificados para quaisquer intervalos sobrepostos. Se você já carregou um arquivo de construção anteriormente, baixe o arquivo atual e carregue-o novamente para identificar quaisquer sobreposições e corrigir o problema antes de carregar novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar nos mapeamentos errados de sub-redes para edifícios nos relatórios. Determinadas implementações vpn não relatam com precisão as informações da sub-rede. 
>
> A coluna VPN é opcional e será padrão para 0. Se o valor da coluna VPN for definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP na sub-rede. Use isso com moderação e somente para sub-redes VPN, pois a expansão completa dessas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a criação de dados. Se a expansão da sub-rede resultar no limite da linha de expansão de 1.000.000 sendo excedido, o arquivo de construção não será aceito.


### <a name="supernetting"></a>Super-rede

Você pode usar a super-rede, comumente chamada cidr (roteamento de Inter-Domain sem classe) no lugar de definir cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço substituído. Há suporte para a super-rede, mas não recomendamos usá-la.

Por exemplo, o edifício de marketing da Contoso é composto pelas sub-redes abaixo:

-   10.1.0.0/24— primeiro andar
-   10.1.1.0/24— segundo andar
-   10.1.2.0/24— terceiro andar
-   10.1.3.0/24— quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço sobrescrito , neste exemplo, 10.1.0.0.0/22.

-   Rede = 10.1.0.0
-   Intervalo de Rede = 22

Aqui estão algumas coisas a serem consideradas antes de implementar a super-rede:

-   A super-rede só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits a 28 bits.

-   A super-rede leva menos tempo na frente, mas vem ao custo de reduzir a riqueza de seus dados. Digamos que há um problema de qualidade envolvendo a sub-rede 10.1.2.0. Se você implementou a super-rede, não saberá onde na construção a sub-rede está localizada ou qual tipo de rede ela é (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes para um edifício e carregado informações de localização do andar, seria possível ver essa distinção.

-   É importante garantir que o endereço substituído esteja correto e não esteja capturando sub-redes indesejadas.

-   É bastante comum encontrar 192.168.0.0 em dados. Para muitas organizações, isso indica que o usuário está em casa. Para outros, este é o esquema de endereço IP de um escritório satélite. Se sua organização tiver escritórios que usam essa configuração, não a inclua em seu arquivo de construção porque é difícil distinguir entre redes domésticas e [internas usando sub-redes comuns](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todos os novos uploads de arquivos de dados de construção serão verificados para quaisquer intervalos sobrepostos. Se você já carregou um arquivo de construção anteriormente, você deve baixar o arquivo atual e carregá-lo novamente para identificar quaisquer sobreposições e corrigir o problema. Qualquer sobreposição em arquivos carregados anteriormente pode resultar nos mapeamentos errados de sub-redes para edifícios nos relatórios.

### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Microsoft 365 ou Office 365 , que é de onde os dados do CQD são provenientes, inclui um sinalizador VPN. O CQD verá isso como as dimensões Primeira VPN e Segunda VPN. No entanto, esse sinalizador depende do relatório dos fornecedores de VPN para o Windows de que o adaptador de rede VPN registrado é um adaptador de Acesso Remoto. Nem todos os fornecedores de VPN registram adequadamente adaptadores de Acesso Remoto. Por causa disso, talvez você não seja capaz de usar os filtros de consulta VPN internos. Use a coluna VPN discutida acima para marcar e identificar com precisão as sub-redes VPN. Também é uma boa prática rotular suas redes VPN para facilitar a identificação em seus relatórios. Veja abaixo dois exemplos de como rotular suas sub-redes VPN:

- Defina um **Nome de Rede** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da rede.](media/qerguide-image-vpnnetworkname.png)

- Defina um **Nome de Construção** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da construção.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> As conexões VPN são conhecidas por identificar erroneamente o tipo de conexão de rede como conectado quando a conexão subjacente é sem fio. Ao examinar a qualidade das conexões VPN, não é possível supor que o tipo de conexão tenha sido identificado com precisão.

## <a name="endpoint-data-file"></a>Arquivo de dados do ponto de extremidade

O outro tipo de arquivo de dados de locatário CQD é o arquivo de dados do **Ponto de Extremidade** . Os valores da coluna são usados na coluna Nome do Primeiro Ponto de Extremidade do Cliente do registro de chamada ou Nome do Segundo Ponto de Extremidade do Cliente para mostrar informações de Ponto de Extremidade Make, Modelo ou Tipo. O formato do arquivo de dados carregado deve atender aos seguintes critérios para passar a verificação de validação antes de carregar:

- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Espera-se que a primeira linha do arquivo de dados seja dados reais, não um rótulo de cabeçalho como "EndpointName".

- Todas as sete colunas usam apenas o tipo de dados String. O comprimento máximo permitido é de 64 caracteres.

- As entradas são sensíveis a casos; EndpointName **ABC123** será tratado como exclusivo do EndpointName **abc123**.

- Um campo de dados pode estar vazio, mas ainda deve ser separado por uma guia ou vírgula. Um campo de dados vazio atribui apenas um valor de cadeia de caracteres vazio.

- EndpointName deve ser exclusivo, caso contrário, o upload falhará. Se houver uma linha duplicada ou duas linhas que usam o mesmo EndpointName, o conflito causará junção incorreta.

- EndpointLabel1, EndpointLabel2 e EndpointLabel3 são rótulos personalizáveis. Elas podem ser cadeias de caracteres vazias ou valores como "Departamento de TI designado 2018 Laptop" ou "Asset Tag 5678".

- Deve haver sete colunas para cada linha e as colunas devem estar na seguinte ordem:

  **Ordem de campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Linha de exemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Atualizar um arquivo de construção

Ao coletar informações de construção e sub-rede, os administradores geralmente carregam o arquivo de construção em várias iterações ao longo do tempo, adicionando novas sub-redes e suas informações de construção à medida que ele se torna disponível. Quando isso ocorrer, você precisará carregar novamente seu arquivo de construção. Esse processo é como o upload inicial, conforme descrito na seção anterior, com algumas exceções, conforme observado na seção a seguir.

> [!Important]
> Somente um arquivo de construção pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

## <a name="add-net-new-subnets"></a>Adicionar novas sub-redes líquidas

Há momentos em que você precisará adicionar novas sub-redes líquidas ao CQD que não eram originalmente parte da topologia de rede. Para adicionar novas sub-redes líquidas, faça o seguinte na página **Carregar Dados do Locatário** no CQD:

1.  Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1.  Remova o arquivo atual no CQD.

1.  Edite o arquivo de construção original e forneça uma data de término que ocorra pelo menos um dia antes da aquisição de novas sub-redes líquidas.

1.  Anexe as novas sub-redes líquidas ao arquivo de construção original.

1.  Carregue o arquivo de construção recém-modificado e defina a data de início para um dia após o término do arquivo de construção anterior.

## <a name="add-missing-subnets"></a>Adicionar sub-redes ausentes

Depois de carregar informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre será o caso; normalmente, algumas sub-redes são perdidas. Para encontrar essas redes ausentes, examine o **Relatório de Sub-rede Ausente** na página **Relatórios de Qualidade da Experiência** no CQD. Isso apresenta todas as sub-redes com 10 ou mais fluxos de áudio que não são definidos no arquivo de dados de construção e estão sendo marcados como externos. Verifique se não há redes gerenciadas nesta lista. Se as sub-redes estiverem ausentes, use o procedimento a seguir para atualizar o arquivo de dados de construção original e carregá-lo novamente no CQD.

1. Acesse a página **Carregar Dados do Locatário** no CQD.

1. Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1. Remova o arquivo atual no CQD.

1. Anexe as novas sub-redes ao arquivo original.

1. Carregue o arquivo de construção. Certifique-se de definir a data de início como pelo menos oito meses antes para que o CQD processe dados históricos.


> [!IMPORTANT]
> Você precisará adicionar sua ID de locatário como um filtro de consulta para **a Segunda ID do Locatário** a este relatório para filtrar o relatório para exibir apenas os dados de locatário da sua organização. Caso contrário, o relatório mostrará sub-redes federadas.

> [!NOTE] 
> Certifique-se de ajustar o filtro de relatório ano mês para o mês atual. Selecione **Editar** e ajuste o filtro de relatório **ano** mês para salvar o novo mês padrão.


## <a name="related-topics"></a>Tópicos relacionados

[Criar um mapa de construção para CQD](CQD-building-mapping.md)

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
