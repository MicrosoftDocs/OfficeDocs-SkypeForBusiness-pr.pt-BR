---
title: Usar Config.xml para executar tarefas de instalação em clientes do Skype for Business
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Resumo: como usar o arquivo Config.xml para especificar instruções de instalação adicionais.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825181"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usar Config.xml para executar tarefas de instalação em clientes do Skype for Business

**Resumo:** Como usar o arquivo Config.xml para especificar instruções de instalação adicionais.

Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:

- Especificar o caminho do ponto de instalação de rede.

- Selecionar os produtos a serem instalados.

- Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.

- Especifique as opções de instalação, como nome do usuário.

- Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.

- Adicionar ou remover idiomas da instalação.

Recomendamos que você use o arquivo Config.xml para configurar a instalação silenciosa do Skype for Business. 

Por padrão, o Config.xml arquivo que está armazenado na pasta principal do produto (por exemplo, \ _produto._ O WW) direciona a Instalação para instalar esse produto. Por exemplo, o Config.xml na seguinte pasta instala o Skype for Business:

- \\server\share\Skype15\Skype.WW \Config.xml

Os Config.xml elementos mais comumente usados para a instalação do Skype for Business estão listados na tabela a seguir.

**Elementos de Config.xml**


| **Elemento**              | **Descrição**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuração  <br/>     | Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync (isso funcionará para clientes do Skype for Business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Especifica como os recusos de produto específicos são manipulados durante a instalação. Use os atributos a seguir para impedir a instalação do Serviços De Conectividade Empresariais, que inclui componentes compartilhados que interferem no Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registro em log  <br/>           | Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes: <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:<br/>  Setting Id=" *name*" (o nome da propriedade do Windows Installer)  <br/>  Value=" *value*" (o valor a ser atribuído à propriedade)  <br/>                                                             |
| DistributionPoint  <br/> | O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:<br/>  Location=" *path*"  <br/>                                                                                                                                     |

O exemplo a seguir mostra um Config.xml para uma instalação silenciosa típica do cliente Skype for Business. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informações detalhadas sobre como usar o arquivo Config.xml para executar tarefas de instalação e manutenção do Office estão disponíveis em [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .

## <a name="to-customize-the-configxml-file"></a>Para personalizar o arquivo Config.xml

1. Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.

2. Localize as linhas que contêm os elementos que você deseja alterar.

3. Modifique a entrada do elemento com as opções silenciosas que você deseja usar. Certifique-se de remover os delimitadores de comentário, " \<!--" and "--\> ". Por exemplo, use a seguinte sintaxe:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salve o arquivo Config.xml.


