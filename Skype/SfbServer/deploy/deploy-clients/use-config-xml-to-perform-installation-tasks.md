---
title: Usar o config. XML para executar tarefas de instalação no Skype para clientes corporativos
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: 285792dbc753d8c16e6d31f83782d53f85c895f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895051"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar o config. XML para executar tarefas de instalação no Skype para clientes corporativos

**Resumo:** como usar o arquivo Config.xml para especificar instruções de instalação adicionais.

Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:

- Especificar o caminho do ponto de instalação de rede.

- Selecionar os produtos a serem instalados.

- Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.

- Especifique as opções de instalação, como nome do usuário.

- Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.

- Adicionar ou remover idiomas da instalação.

Recomendamos que você use o arquivo config. XML para configurar o Skype para instalação silenciosa de negócios. 

Por padrão, o arquivo config. XML que é armazenado na pasta principal do produto (por exemplo, \ _produto_. WW) direciona a instalação para instalar o produto. Por exemplo, o arquivo config. XML na pasta a seguir instala Skype para negócios:

- \\server\share\Skype15\Skype.WW \Config.xml

Os elementos do config. XML mais comuns utilizados para Skype para instalação de negócios são listados na tabela a seguir.

**Elementos de Config.xml**


| **Elemento**              | **Descrição**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuração  <br/>     | Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (funcionará para clientes do Skype for Business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica como os recursos específicos de produto são manipulados durante a instalação. Use os seguintes atributos para evitar a instalação dos serviços corporativos de conectividade, que inclui os componentes compartilhados que interferem no Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Exibir  <br/>           | O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes: <br/>  CompletionNotice = "Yes"                                                                                                                                                                                |
| Registro em log  <br/>           | Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes: <br/>  Tipo = "Off"                                                                                                                                                                                       |
| Configuração  <br/>           | Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:<br/>  Setting Id = " *nome*" (o nome da propriedade do Windows Installer)  <br/>  Valor = " *valor*" (o valor a ser atribuído à propriedade)  <br/>                                                             |
| DistributionPoint  <br/> | O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:<br/>  Local = " *caminho*"  <br/>                                                                                                                                     |

O exemplo a seguir mostra um arquivo config. XML para uma instalação silenciosa típica do Skype para o cliente de negócios. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informações detalhadas sobre como usar o arquivo config. XML para executar tarefas de instalação e manutenção do Office estão disponíveis em [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).

## <a name="to-customize-the-configxml-file"></a>Para personalizar o arquivo Config.xml

1. Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.

2. Localize as linhas que contêm os elementos que você deseja alterar.

3. Modifique a entrada do elemento com as opções silenciosas que você deseja usar. Certifique-se de que você remova os delimitadores de comentário, "\<! –" e "–\>". Por exemplo, use a seguinte sintaxe:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salve o arquivo Config.xml.


