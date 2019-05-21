---
title: Instalar a Ferramenta de Planejamento no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a ferramenta de planejamento do Skype for Business Server 2015, você deve primeiro instalar a ferramenta de planejamento. A ferramenta de planejamento não precisa ser implantada em uma estação de trabalho ou em um servidor que faça parte do domínio ou da infraestrutura em que você planeja instalar o Skype for Business Server 2015. O arquivo Leiame que acompanha a ferramenta de planejamento detalha informações importantes sobre a instalação e a utilização da ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279124"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar a Ferramenta de Planejamento no Skype for Business Server 2015

Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a ferramenta de planejamento do Skype for Business Server 2015, você deve primeiro instalar a ferramenta de planejamento. A ferramenta de planejamento não precisa ser implantada em uma estação de trabalho ou em um servidor que faça parte do domínio ou da infraestrutura em que você planeja instalar o Skype for Business Server 2015. O arquivo Leiame que acompanha a ferramenta de planejamento detalha informações importantes sobre a instalação e a utilização da ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.

> [!IMPORTANT]
> A ferramenta de planejamento requer a instalação de um usuário com direitos e permissões de administrador no computador em que a ferramenta está instalada.

Os sistemas operacionais com suporte para instalação e operação da ferramenta de planejamento são:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, edição de 32 bits

- Windows 7, edição de 64 bits usando Windows no Win32 (WOW)

- Windows Server 2008 R2, usando WOW

Além disso, a ferramenta de planejamento requer o Microsoft .NET Framework 4,5.

Depois que os requisitos de pré-instalação forem atendidos, você poderá instalar a ferramenta de planejamento.



## <a name="to-install-the-planning-tool"></a>Para instalar a Ferramenta de Planejamento

1. Faça logon no computador local como membro do grupo Administradores.

2. Usando o Windows Explorer ou uma janela de comando, localize o diretório em que você baixou os arquivos de instalação da ferramenta de planejamento.

3. Localize o SkypeForBusinessPlanningTool.msi. No Windows Explorer, clique duas vezes no arquivo. Na janela de comando, digite o nome do arquivo e pressione  **Enter** para executá-lo.

4. Na página de Boas-vindas do **Skype for Business Server 2015, Assistente de instalação da ferramenta de planejamento **, clique em **Avançar**.

5. Revise o **Contrato de Licença de Usuário Final**, selecione **Aceito os termos do Contrato de Licença** se você escolher aceitar os termos de uso do contrato de licença e clique em **Avançar**.

6. Escolha onde instalar os arquivos da ferramenta de planejamento. O local padrão é C:\Arquivos de Programas (x86)\Skype for Business Server 2015\Ferramenta de planejamento. Se quiser alterar o local de instalação, clique em **Alterar**. Em **Alterar pasta de destino**, procure ou digite o local para instalar os arquivos, clique em **OK** e, depois, em **Avançar**.

7. O instalador já está pronto para instalar a ferramenta de planejamento. Clique em **Instalar** para começar o processo de instalação.

8. A instalação será iniciada e o andamento será exibido. Após a conclusão da instalação, clique em **Concluir**.

9. A ferramenta de planejamento está pronta para uso.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

A ferramenta de planejamento do Skype for Business Server 2015 foi projetada para exportar para o Microsoft Excel e o Microsoft Visio. Embora esses aplicativos não sejam necessários para a operação da ferramenta de planejamento, eles adicionam um valor significativo à implantação e à documentação do seu design.

### <a name="microsoft-excel"></a>Microsoft Excel

Exportar seu design para Microsoft Excel cria um relatório que exibe sete guias na planilha:

- Resumo – exibe informações sobre a configuração do site, incluindo a contagem de usuários, configurações de capacidade e informações de perfil do servidor.

- Perfil de hardware – exibe um relatório sobre as configurações de hardware recomendadas para os servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede. Também está incluída a quantidade e especificações recomendadas para os componentes do servidor. Cada servidor também é definido por site, para fornecer uma representação completa dos requisitos de servidor por cada site.

- Requisitos de portas – exibe um relatório de todas as portas habilitadas e a associação ao balanceamento de carga do sistema de nome de domínio (DNS LB) e aos balanceadores de carga de hardware (HLB). Esse relatório deve ser usado para planejar suas configurações de firewall e DNS LB e HLB.

- Relatório de resumo-mostra o resumo geral das configurações necessárias para configurar sua rede de servidor de borda.

- Relatório de certificados-mostra o nome do requerente e os nomes alternativos de assunto que são necessários para os certificados necessários para obter os servidores de borda em execução.

- Relatório de firewall-exibe as portas de origem e de destino e os endereços IP para interfaces internas e externas.

- Relatório DNS-exibe o nome de domínio totalmente qualificado (FQDN) e os endereços IP/VIP necessários para cada entrada DNS que você criar.

### <a name="microsoft-visio"></a>Microsoft Visio

Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:

> [!NOTE]
> Se o seu design for grande o suficiente para exigir mais do que três servidores front-end, uma página adicional será criada para o pool de front-end, servidores front-end, o computador que executa o SQL Server, endereços IP e FQDNs.

- Topologia global-diagrama de sites configurados do Skype for Business Server 2015.

- Guia nome do site-exibe a topologia de configuração do site com o servidor de borda, o firewall, a PSTN (rede telefônica pública comutada) com gateways e a implantação de servidor interno. A implantação interna consiste em servidores e pools configurados, incluindo os pools de front-end, servidores baseados no SQL Server, serviços de domínio Active Directory, directors, servidores Exchange Unified Messaging (UM), servidores de caixa de correio do Exchange, servidores do Office Web Apps Servidores de mediação e servidores de chat persistentes.

- Diagrama de rede de borda – detalhando a configuração do servidor de borda com endereços IP e FQDNs associados. Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos. Além disso, os diretores e o servidor front-end ou o pool de front-end são exibidos com o DNS LB ou o HLB associado e o endereço IP atribuído (a ferramenta de planejamento oferece suporte aos endereços IPv4 e IPv6) e ao FQDN.

## <a name="see-also"></a>Confira também
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
