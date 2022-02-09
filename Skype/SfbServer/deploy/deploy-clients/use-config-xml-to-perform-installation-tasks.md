---
title: Usar Config.xml para executar tarefas de instalação em Skype for Business clientes
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: b90fac846a8c2707d95103d776c37ffefd0e1ec6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404403"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar Config.xml para executar tarefas de instalação em Skype for Business clientes

**Resumo:** Como usar o arquivo Config.xml para especificar instruções de instalação adicionais.

Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:

- Especificar o caminho do ponto de instalação de rede.

- Selecionar os produtos a serem instalados.

- Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.

- Especifique as opções de instalação, como nome do usuário.

- Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.

- Adicionar ou remover idiomas da instalação.

Recomendamos que você use o arquivo Config.xml para configurar Skype for Business instalação silenciosa. 

Por padrão, o arquivo Config.xml que é armazenado na pasta principal do produto (por exemplo, \ _produto_. WW) direciona a Instalação para instalar esse produto. Por exemplo, o arquivo Config.xml na pasta a seguir instala Skype for Business:

- \\server\share\Skype15\Skype. WW \Config.xml

Os Config.xml mais comumente usados para Skype for Business instalação são listados na tabela a seguir.

**Elementos de Config.xml**


| **Elemento**              | **Descrição**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuração  <br/>     | Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (Isso funcionará para Skype for Business clientes)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica como os recusos de produto específicos são manipulados durante a instalação. Use os atributos a seguir para impedir a instalação de Serviços Corporativos de Conectividade, que inclui componentes compartilhados que interferem no Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registrar em log  <br/>           | Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes: <br/>  Digite ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:<br/>  Definindo Id=" *name*" (o nome da propriedade Windows Installer)  <br/>  Valor=" *(* o valor a ser atribuído à propriedade)  <br/>                                                             |
| DistributionPoint  <br/> | O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:<br/>  Caminho Location *="*  <br/>                                                                                                                                     |

O exemplo a seguir mostra um arquivo Config.xml para uma instalação silenciosa típica do Skype for Business cliente. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informações detalhadas sobre como usar o arquivo Config.xml para executar Office tarefas de instalação e manutenção estão disponíveis em [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)).

## <a name="to-customize-the-configxml-file"></a>Para personalizar o arquivo Config.xml

1. Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.

2. Localize as linhas que contêm os elementos que você deseja alterar.

3. Modifique a entrada do elemento com as opções silenciosas que você deseja usar. Certifique-se de remover os delimitadores de comentários, "\<!--" and "--\>". Por exemplo, use a seguinte sintaxe:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salve o arquivo Config.xml.