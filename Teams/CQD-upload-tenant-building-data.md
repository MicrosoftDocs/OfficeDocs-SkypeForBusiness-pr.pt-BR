---
title: Upload locatário e a criação de dados no Painel de Qualidade de Chamada (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como carregar locatários e criar dados no Painel de Qualidade de Chamada (CQD).
ms.openlocfilehash: c3da64a66ec2e78165bd0ee9dcb50acbe7739ee4
ms.sourcegitcommit: 0486ca906fc7f66460e54e400541e5d5cbfc6dde
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2022
ms.locfileid: "62160970"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Upload locatário e a criação de dados no Painel de Qualidade de Chamada (CQD)


Para obter o máximo do CQD (Painel de Qualidade de Chamada), recomendamos carregar seu locatário e criar dados. Há 2 tipos de arquivos de dados de locatários, [Building](#upload-building-data-file) e [Endpoint](#endpoint-data-file).

Você pode baixar um modelo de dados de locatário de [exemplo aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Para ajudar a criar mapeamento, leia [Criar um mapa de construção para CQD](CQD-building-mapping.md).

No painel Relatórios de Resumo do CQD, selecione Dados do **Locatário Upload** no **menu** Configurações CQD (um ícone de engrenagem na parte superior do CQD). A partir daqui, os administradores podem carregar informações de criação e ponto de extremidade da organização, como mapeamento de endereços IP e informações geográficas, mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.

1. Abra o CQD (no centro de administração do Teams ou em ), selecione o ícone de engrenagem no canto superior direito e escolha Dados do Locatário Upload na página Relatórios de [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Resumo.  

   ![Captura de tela da caixa de diálogo que aparece enquanto os dados estão sendo carregados.](media/qerguide-image-tenantdataupload.png)
    
2. Como alternativa, se essa for sua primeira vez visitando o CQD, você será solicitado a carregar dados de construção. Você pode selecionar **Upload Agora** para navegar rapidamente até a página **De Upload** locatário.

   ![Captura de tela do banner que notifica um usuário para carregar dados de construção.](media/qerguide-image-buildingdatauploadbanner.png)

3. Na página **Dados do Locatário Upload,** selecione **Procurar** para escolher um arquivo de dados.

4. Depois de selecionar um arquivo de dados, especifique a data **de** início e, opcionalmente, especifique uma data de término.

5. Depois de **selecionar a data de** início, selecione **Upload** para carregar o arquivo no CQD. <br><br>Antes de carregar o arquivo, ele é validado. Se a validação falhar, uma mensagem de erro será exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorre quando o número de colunas no arquivo de dados está incorreto.

   ![Exemplo de caixa de diálogo exibindo um erro de carregamento de dados de construção.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se nenhum erro ocorrer durante a validação, o carregamento de arquivo será bem-sucedido. Em seguida, você pode ver o arquivo de dados carregado na tabela **Meus carregamentos,** que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior dessa página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já carregou um arquivo de construção e precisa adicionar sub-redes que podem ter sido perdidas ou excluídas, modifique o arquivo original adicionando as novas sub-redes, remova o arquivo atual e carregue novamente o arquivo recém-editado. Pode haver apenas um arquivo de dados de construção ativo no CQD. 


## <a name="upload-building-data-file"></a>Upload criar arquivo de dados

O primeiro tipo de arquivo de dados de locatário no CQD é o **arquivo de dados de** criação. A coluna Sub-rede é derivada expandindo a coluna Network+NetworkRange e, em seguida, unindo a coluna Sub-rede à primeira sub-rede ou segunda sub-rede do registro de chamada para mostrar informações de construção, cidade, país ou região. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes de carregar:
  
- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O arquivo de dados não inclui uma linha de header de tabela. Espera-se que a primeira linha do arquivo de dados seja de dados reais, e não rótulos de header como "Network".

- Os tipos de dados no arquivo só podem ser String, Integer ou Boolean. Para o tipo de dados Integer, o valor deve ser um valor numérico. Os valores booleanos devem ser 0 ou 1.

- Se uma coluna usa o tipo de dados String, um campo de dados pode estar vazio, mas ainda deve ser separado por uma guia ou vírgula. Um campo de dados vazio apenas atribui um valor String vazio.

- Há um limite de linha de 1.000.000 por arquivo de dados de locatário.

- Deve haver 15 colunas para cada linha, cada coluna deve ter o tipo de dados apropriado e as colunas devem estar na ordem listada na tabela a seguir (vírgula ou tabulação delimitada):

  **Criar formato de arquivo de dados**
  
  | Nome da coluna        | Tipo de dados | Exemplo                   | Orientação              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Cadeia de caracteres    | 192.168.1.0               | Obrigatório              |
  | NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-SEA-1 | Obrigatório<sup>1</sup>  |
  | NetworkRange       | Número    | 26                        | Obrigatório              |
  | BuildingName       | Cadeia de caracteres    | SEATTLE-SEA-1             | Obrigatório<sup>1</sup>  |
  | OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional              |
  | BuildingType       | Cadeia de caracteres    | Terminação de IT            | Opcional              |
  | BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional              |
  | Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado           |
  | ZipCode            | Cadeia de caracteres    | 98001                     | Recomendado           |
  | País            | Cadeia de caracteres    | EUA                        | Recomendado           |
  | Estado              | Cadeia de caracteres    | WA                        | Recomendado           |
  | Região             | Cadeia de caracteres    | MSUS                      | Recomendado           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obrigatório              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obrigatório              |
  | VPN                | Bool      | 0                         | Opcional              |

  <sup>1</sup> Embora não seja exigido pelo CQD, os modelos são configurados para exibir o nome de construção e rede.

  <sup>2</sup> Essa configuração pode ser usada para refletir se a sub-rede está ou não dentro da rede corporativa. Você pode personalizar o uso para outras finalidades.

  <sup>3</sup> Essa configuração pode ser usada para refletir se a rede usa ou não o Azure ExpressRoute. Você pode personalizar o uso para outras finalidades.  

  **Linha de exemplo:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados em busca de intervalos sobrepostos. Se você tiver carregado anteriormente um arquivo de construção, baixe o arquivo atual e o carregue novamente para identificar quaisquer sobreposições e corrigir o problema antes de carregar novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para edifícios nos relatórios. Determinadas implementações vpn não relatam com precisão as informações da sub-rede. 
>
> A coluna VPN é opcional e será padrão como 0. Se o valor da coluna VPN for definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede. Use isso com moderação e somente para sub-redes VPN, pois a expansão total dessas sub-redes terá um impacto negativo nos tempos de consulta para consultas envolvendo a criação de dados. Se a expansão da sub-rede resulta no limite de linha de expansão de 1.000.000 sendo excedido, o arquivo de construção não será aceito.


### <a name="supernetting"></a>Supernetting

Você pode usar a supernetização, comumente chamada roteamento sem classe Inter-Domain (CIDR,) em vez de definir cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sobre-vinhedo. Há suporte para a super-rede, mas não recomendamos usá-la.

Por exemplo, a criação de marketing da Contoso é feita das sub-redes abaixo:

-   10.1.0.0/24— primeiro andar
-   10.1.1.0/24— segundo andar
-   10.1.2.0/24— terceiro andar
-   10.1.3.0/24— quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sobre-vinhedo, neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0
-   Intervalo de rede = 22

Aqui estão algumas coisas a considerar antes de implementar a super-rede:

-   A supernetação só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits a 28 bits.

-   A supernetação leva menos tempo à frente, mas ela vem com o custo de reduzir a riqueza de seus dados. Digamos que haja um problema de qualidade envolvendo a sub-rede 10.1.2.0. Se você implementou a super-rede, não saberá onde, no edifício, a sub-rede está localizada ou que tipo de rede ela é (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes para um edifício e carregado informações de local de piso, você seria capaz de ver essa distinção.

-   É importante garantir que o endereço com sobrenquete está correto e não está capturando sub-redes indesejadas.

-   É bastante comum encontrar 192.168.0.0 em dados. Para muitas organizações, isso indica que o usuário está em casa. Para outros, esse é o esquema de endereço IP para um escritório via satélite. Se a sua organização tem escritórios que usam essa configuração, não a inclua no arquivo de construção porque é difícil distinguir entre redes internas e internas usando [sub-redes comuns.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todos os novos carregamentos de arquivos de dados de construção serão verificados em busca de intervalos sobrepostos. Se você tiver carregado um arquivo de construção anteriormente, baixe o arquivo atual e carregue-o novamente para identificar quaisquer sobreposições e corrigir o problema. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para edifícios nos relatórios.

### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Microsoft 365 ou Office 365 — que é de onde os dados CQD são fonte — inclui um sinalizador VPN. O CQD verá isso como as primeiras dimensões VPN e Segunda VPN. No entanto, esse sinalizador se baseia no relatório de fornecedores vpn para Windows que o adaptador de rede VPN registrado é um adaptador de Acesso Remoto. Nem todos os fornecedores VPN registram adequadamente adaptadores de Acesso Remoto. Por isso, talvez você não consiga usar os filtros de consulta VPN integrados. Use a coluna VPN abordada acima para marcar e identificar com precisão as sub-redes VPN. Também é uma boa prática rotular suas redes VPN para facilitar a identificação em seus relatórios. A seguir estão dois exemplos de como rotular suas sub-redes VPN:

- Defina **um Nome de Rede** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da rede.](media/qerguide-image-vpnnetworkname.png)

- Defina **um Nome de Construção** inserindo "VPN" neste campo para sub-redes VPN.

  ![Captura de tela de relatório de QCD mostrando VPN usando nome de construção.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> As conexões VPN são conhecidas por identificar erromente o tipo de conexão de rede como com fio quando a conexão subjacente é sem fio. Ao ver a qualidade sobre conexões VPN, não é possível supor que o tipo de conexão foi identificado com precisão.

## <a name="endpoint-data-file"></a>Arquivo de dados do ponto de extremidade

O outro tipo de arquivo de dados de locatário CQD é o **arquivo de dados** do Ponto de Extremidade. Os valores da coluna são usados na coluna Nome do Ponto de Extremidade do Primeiro Cliente do registro de chamada ou na coluna Nome do Ponto de Extremidade do Segundo Cliente para mostrar informações do Ponto de Extremidade Make, Model ou Type. O formato do arquivo de dados que você carrega deve atender aos seguintes critérios para passar a verificação de validação antes de carregar:

- O arquivo deve ser um arquivo .tsv (as colunas são separadas por um TAB) ou um arquivo .csv (as colunas são separadas por uma vírgula).

- O conteúdo do arquivo de dados não inclui os headers de tabela. Espera-se que a primeira linha do arquivo de dados sejam dados reais, não um rótulo de header como "EndpointName".

- Todas as sete colunas usam somente o tipo de dados String. O comprimento máximo permitido é de 64 caracteres.

- As entradas são sensíveis a minúsculas; EndpointName **ABC123** será tratado como exclusivo do EndpointName **abc123**.

- Um campo de dados pode estar vazio, mas ainda deve ser separado por uma guia ou vírgula. Um campo de dados vazio apenas atribui um valor String vazio.

- EndpointName deve ser exclusivo, caso contrário, o carregamento falhará. Se houver uma linha duplicada ou duas linhas que usem o mesmo EndpointName, o conflito causará uma junção incorreta.

- EndpointLabel1, EndpointLabel2 e EndpointLabel3 são rótulos personalizáveis. Eles podem ser strings ou valores vazios, como "Departamento de IT designado laptop 2018" ou "Asset Tag 5678".

- Deve haver sete colunas para cada linha e as colunas devem estar na seguinte ordem:

  **Ordem de campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Linha de exemplo:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Atualizar um arquivo de construção

Ao coletar informações de construção e sub-rede, os administradores geralmente carregam o arquivo de construção em várias iterações ao longo do tempo, adicionando novas sub-redes e suas informações de construção à medida que ele se torna disponível. Quando isso ocorrer, você precisará carregar seu arquivo de construção de novo. Esse processo é como o carregamento inicial, conforme descrito na seção anterior, com algumas exceções, conforme descrito na seção a seguir.

> [!Important]
> Somente um arquivo de construção pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

## <a name="add-net-new-subnets"></a>Adicionar novas sub-redes líquidas

Há momentos em que você precisará adicionar novas sub-redes líquidas ao CQD que não eram originalmente parte de sua topologia de rede. Para adicionar novas sub-redes líquidas, faça o seguinte na página Dados **do Locatário Upload** CQD:

1.  Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1.  Remova o arquivo atual no CQD.

1.  Edite o arquivo de construção original e forneça uma data de término que ocorre pelo menos um dia antes da aquisição das novas sub-redes líquidas.

1.  Anexar as novas sub-redes líquidas ao arquivo de construção original.

1.  Upload o arquivo de construção recém-modificado e de definir a data de início para um dia após o final do arquivo de construção anterior.

## <a name="add-missing-subnets"></a>Adicionar sub-redes ausentes

Depois de carregar informações de construção para redes gerenciadas, todas as redes gerenciadas devem ter uma associação de construção. No entanto, isso nem sempre será o caso; normalmente, algumas sub-redes são perdidas. Para encontrar essas redes ausentes, revise o Relatório de **Sub-rede** Ausente na página Relatórios de Qualidade da **Experiência** no CQD. Isso apresenta todas as sub-redes com 10 ou mais fluxos de áudio que não são definidos no arquivo de dados de construção e estão sendo marcados como fora. Verifique se não há redes gerenciadas nesta lista. Se as sub-redes estão ausentes, use o procedimento a seguir para atualizar o arquivo de dados de construção original e recarná-lo no CQD.

1. Vá para a **página Dados do Locatário Upload** CQD.

1. Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.

1. Remova o arquivo atual no CQD.

1. Anexar as novas sub-redes ao arquivo original.

1. Upload o arquivo de construção. Certifique-se de definir a data de início como pelo menos oito meses antes para que o CQD processe dados históricos.


> [!IMPORTANT]
> Você precisará adicionar sua ID de locatário como um filtro de consulta para a **segunda ID** de locatário a este relatório para filtrar o relatório para exibir apenas os dados de locatários da sua organização. Caso contrário, o relatório mostrará sub-redes federadas.

> [!NOTE] 
> Certifique-se de ajustar o filtro de relatório de Ano Mensal ao mês atual. Selecione **Editar** e ajuste o filtro de relatório **Ano** Mensal para salvar o novo mês padrão.


## <a name="related-topics"></a>Tópicos relacionados

[Criar um mapa de construção para CQD](CQD-building-mapping.md)

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade de chamada e reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
