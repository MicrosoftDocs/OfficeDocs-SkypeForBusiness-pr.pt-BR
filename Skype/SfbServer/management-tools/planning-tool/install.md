---
title: Instalar a Ferramenta de Planejamento no Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de começar Projetando e planejar seu Skype para infraestrutura de Business Server 2015 usando o Skype para ferramenta de planejamento do Business Server 2015, primeiro você deve instalar a ferramenta de planejamento. A ferramenta de planejamento não precisa ser implantado em uma estação de trabalho ou um servidor que faz parte do domínio ou da infra-estrutura onde você planeja instalar Skype para Business Server 2015. O arquivo Leiame que acompanha a ferramenta de planejamento detalha as informações importantes sobre como instalar e usar a ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.
ms.openlocfilehash: 616cec026dfc5890cffc3975ea421d98ec13e412
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884129"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar a Ferramenta de Planejamento no Skype for Business Server 2015

Antes de começar Projetando e planejar seu Skype para infraestrutura de Business Server 2015 usando o Skype para ferramenta de planejamento do Business Server 2015, primeiro você deve instalar a ferramenta de planejamento. A ferramenta de planejamento não precisa ser implantado em uma estação de trabalho ou um servidor que faz parte do domínio ou da infra-estrutura onde você planeja instalar Skype para Business Server 2015. O arquivo Leiame que acompanha a ferramenta de planejamento detalha as informações importantes sobre como instalar e usar a ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.

> [!IMPORTANT]
> A ferramenta de planejamento requer a instalação por um usuário com direitos de administrador e permissões no computador no qual a ferramenta está para ser instalado.

Os sistemas operacionais suportados para instalação e operação da ferramenta de planejamento são:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, edição de 32 bits

- Windows 7, edição de 64 bits usando Windows no Win32 (WOW)

- Windows Server 2008 R2, usando WOW

Além disso, a ferramenta de planejamento requer o Microsoft .NET Framework 4.5.

Depois que forem atendidos os requisitos de pré-instalação, você pode instalar a ferramenta de planejamento.



## <a name="to-install-the-planning-tool"></a>Para instalar a Ferramenta de Planejamento

1. Faça logon no computador local como membro do grupo Administradores.

2. Usando o Windows Explorer ou em uma janela de comando, localize o diretório onde você baixou os arquivos de instalação da ferramenta de planejamento.

3. Localize o SkypeForBusinessPlanningTool.msi. No Windows Explorer, clique duas vezes no arquivo. Na janela de comando, digite o nome do arquivo e pressione  **Enter** para executá-lo.

4. Na página de Boas-vindas do **Skype for Business Server 2015, Assistente de instalação da ferramenta de planejamento **, clique em **Avançar**.

5. Revise o **Contrato de Licença de Usuário Final**, selecione **Aceito os termos do Contrato de Licença** se você escolher aceitar os termos de uso do contrato de licença e clique em **Avançar**.

6. Escolha onde instalar os arquivos da ferramenta de planejamento. O local padrão é C:\Arquivos de Programas (x86)\Skype for Business Server 2015\Ferramenta de planejamento. Se quiser alterar o local de instalação, clique em **Alterar**. Em **Alterar pasta de destino**, procure ou digite o local para instalar os arquivos, clique em **OK** e, depois, em **Avançar**.

7. O instalador está pronto para instalar a ferramenta de planejamento. Clique em **Instalar** para começar o processo de instalação.

8. A instalação será iniciada e o andamento será exibido. Após a conclusão da instalação, clique em **Concluir**.

9. A ferramenta de planejamento está pronta para uso.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

O Skype para ferramenta de planejamento do Business Server 2015 foi projetado para exportar para o Microsoft Excel e o Microsoft Visio. Enquanto esses aplicativos não são necessários para a operação da ferramenta de planejamento, eles adicionar um valor significativo para a implantação e a documentação do seu design.

### <a name="microsoft-excel"></a>Microsoft Excel

Exportar seu design para Microsoft Excel cria um relatório que exibe sete guias na planilha:

- Resumo - exibe informações sobre a configuração de site, incluindo a contagem de usuário, configurações de capacidade e informações de perfil do servidor.

- Perfil de hardware - exibe um relatório sobre as configurações de hardware recomendado para servidores que são especificados na topologia, incluindo CPU, memória, disco e interface de rede. Também está incluída a quantidade e especificações recomendadas para os componentes do servidor. Cada servidor também é definido por site, para fornecer uma representação completa dos requisitos de servidor por cada site.

- Requisitos de portas - exibe um relatório de todas as portas que estão habilitadas e a associação (DNS LB) de balanceamento de carga de sistema de nomes de domínio e balanceadores de carga de hardware (HLB). Esse relatório deve ser usado para planejar suas configurações de firewall e DNS LB e HLB.

- Relatório de resumo - exibe o resumo geral das configurações que são necessárias para configurar sua rede de servidor de borda.

- Relatório de certificados - exibe o nome da entidade e nomes alternativos da entidade necessários para os certificados necessários para obter os servidores de borda em execução.

- Relatório - exibe as portas de origem e destino e endereços IP para interfaces externa e interna do firewall.

- Relatório DNS - exibe o nome de domínio totalmente qualificado (FQDN) e endereços IP/VIP exigidas para cada entrada DNS que você criar.

### <a name="microsoft-visio"></a>Microsoft Visio

Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:

> [!NOTE]
> Se seu projeto for grande o suficiente para exigir mais de três servidores Front-End, uma página adicional será criada para o pool de Front-End, servidores Front-End, o computador que executa o SQL Server, endereços IP e FQDNs.

- Topologia global - diagrama do Skype configurado para sites corporativos Server 2015.

- Guia de nome de site - exibe a topologia de configuração de site com o servidor de borda, firewall, pública comutada (PSTN) de rede com gateways e a implantação de servidor interno de telefone. Implantação interna consistir em servidores configurados e pools de pools, incluindo o Front-End, servidores baseados no SQL Server, serviços de domínio do Active Directory, diretores, Exchange Unified Messaging (UM) servidores, servidores de caixa de correio do Exchange, Office Web Apps Servers Os servidores de mediação e servidores de Chat persistente.

- Diagrama de rede - diagrama detalhando a configuração do servidor de borda com endereços IP e FQDNs associados de borda. Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos. Além disso, os diretores e o pool de Front-End ou de servidor Front-End são exibidos, com LB de DNS associado ou HLB e o endereço IP atribuído (a ferramenta de planejamento oferece suporte a endereços IPv4 e IPv6) e o FQDN.

## <a name="see-also"></a>Consulte Também
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
