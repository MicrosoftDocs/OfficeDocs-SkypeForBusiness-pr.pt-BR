---
title: Use config. xml para executar tarefas de instalação em clientes Skype for Business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: 31ee6c663822c2dab59a21fe5ca80c71cb81abf8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234818"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Use config. xml para executar tarefas de instalação em clientes Skype for Business

**Resumo:** como usar o arquivo Config.xml para especificar instruções de instalação adicionais.

Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:

- Especificar o caminho do ponto de instalação de rede.

- Selecionar os produtos a serem instalados.

- Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.

- Especifique as opções de instalação, como nome do usuário.

- Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.

- Adicionar ou remover idiomas da instalação.

Recomendamos que você use o arquivo config. xml para configurar a instalação silenciosa do Skype for Business. 

Por padrão, o arquivo config. xml armazenado na pasta principal do produto (por exemplo, \ _produto_. WW) instrui a instalação a instalar esse produto. Por exemplo, o arquivo config. xml na seguinte pasta instala o Skype for Business:

- \\server\share\Skype15\Skype.WW \Config.xml

Os elementos config. xml mais comumente usados para a instalação do Skype for Business estão listados na tabela a seguir.

**Elementos de Config.xml**


| **Elemento**              | **Descrição**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuração  <br/>     | Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (funcionará para clientes do Skype for Business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica como os recursos específicos de produto são manipulados durante a instalação. Use os atributos a seguir para impedir a instalação de serviços corporativos de conectividade, que incluem componentes compartilhados que interferem no Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Exibir  <br/>           | O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes: <br/>  CompletionNotice = "Sim"                                                                                                                                                                                |
| Registro em log  <br/>           | Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes: <br/>  Digite = "desativado"                                                                                                                                                                                       |
| Configuração  <br/>           | Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:<br/>  Setting ID = " *Name*" (o nome da Propriedade do Windows Installer)  <br/>  Valor = " *valor*" (o valor a ser atribuído à propriedade)  <br/>                                                             |
| DistributionPoint  <br/> | O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:<br/>  Location = " *caminho*"  <br/>                                                                                                                                     |

O exemplo a seguir mostra um arquivo config. xml para uma instalação silenciosa típica do cliente Skype for Business. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informações detalhadas sobre como usar o arquivo config. xml para executar tarefas de instalação e manutenção do Office [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)estão disponíveis em.

## <a name="to-customize-the-configxml-file"></a>Para personalizar o arquivo Config.xml

1. Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.

2. Localize as linhas que contêm os elementos que você deseja alterar.

3. Modifique a entrada do elemento com as opções silenciosas que você deseja usar. Certifique-se de remover os delimitadores de comentário "\<!--" e "--\>". Por exemplo, use a seguinte sintaxe:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salve o arquivo Config.xml.


