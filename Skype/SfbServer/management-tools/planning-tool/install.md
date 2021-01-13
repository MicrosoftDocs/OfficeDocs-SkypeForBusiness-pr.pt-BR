---
title: Instalar a Ferramenta de Planejamento no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a Ferramenta de Planejamento do Skype for Business Server 2015, você deve instalar primeiro a Ferramenta de Planejamento. A Ferramenta de Planejamento não precisa ser implantada em uma estação de trabalho ou servidor que faça parte do domínio ou da infraestrutura onde você planeja instalar o Skype for Business Server 2015. O arquivo Leiame que acompanha a Ferramenta de Planejamento detalha informações importantes sobre como instalar e usar a ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834721"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar a Ferramenta de Planejamento no Skype for Business Server 2015

Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a Ferramenta de Planejamento do Skype for Business Server 2015, você deve instalar primeiro a Ferramenta de Planejamento. A Ferramenta de Planejamento não precisa ser implantada em uma estação de trabalho ou servidor que faça parte do domínio ou da infraestrutura onde você planeja instalar o Skype for Business Server 2015. O arquivo Leiame que acompanha a Ferramenta de Planejamento detalha informações importantes sobre como instalar e usar a ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.

> [!IMPORTANT]
> A Ferramenta de Planejamento exige a instalação por um usuário com direitos e permissões de administrador no computador no qual a ferramenta deve ser instalada.

Os sistemas operacionais suportados para instalação e operação da Ferramenta de Planejamento são:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, edição de 32 bits

- Windows 7, edição de 64 bits usando Windows no Win32 (WOW)

- Windows Server 2008 R2, usando WOW

Além disso, a Ferramenta de Planejamento requer o Microsoft .NET Framework 4.5.

Depois que os requisitos de pré-instalação são atendidos, você pode instalar a Ferramenta de Planejamento.



## <a name="to-install-the-planning-tool"></a>Para instalar a Ferramenta de Planejamento

1. Faça logoff no computador local como membro do grupo Administradores.

2. Usando o Windows Explorer ou uma janela de comando, localize o diretório onde você baixou os arquivos de instalação da Ferramenta de Planejamento.

3. Localize o SkypeForBusinessPlanningTool.msi. No Windows Explorer, clique duas vezes no arquivo. Na janela de comando, digite o nome do arquivo e pressione **Enter** para executar o arquivo.

4. Na página de boas-vindas do **Skype for Business Server 2015, Assistente** de Configuração da Ferramenta de Planejamento, clique em **Próximo.**

5. Revise o **Contrato de Licença de Usuário Final**, selecione **Aceito os termos do Contrato de Licença** se você escolher aceitar os termos de uso do contrato de licença e clique em **Avançar**.

6. Escolha onde instalar os arquivos da Ferramenta de Planejamento. O local padrão é C:\Arquivos de Programas (x86)\Skype for Business Server 2015\Ferramenta de Planejamento. Se você quiser alterar o local de instalação, clique em **Alterar**. Em **Alterar pasta de destino**, procure ou digite o local para instalar os arquivos, clique em **OK** e clique em **Avançar**.

7. O instalador agora está pronto para instalar a Ferramenta de Planejamento. Clique em **Instalar** para começar o processo de instalação.

8. A instalação será iniciada e o andamento será exibido. Após a conclusão da instalação, clique em **Concluir**.

9. A Ferramenta de Planejamento está pronta para uso.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

A Ferramenta de Planejamento do Skype for Business Server 2015 foi projetada para exportar para o Microsoft Excel e o Microsoft Visio. Embora esses aplicativos não sejam necessários para a operação da Ferramenta de Planejamento, eles agregam valor significativo à implantação e documentação do seu design.

### <a name="microsoft-excel"></a>Microsoft Excel

Exportar seu design para o Microsoft Excel cria um relatório que exibe sete guias na planilha:

- Resumo - Exibe informações sobre a configuração do site, incluindo contagem de usuários, configurações de capacidade e informações de perfil de servidor.

- Perfil de Hardware - Exibe um relatório sobre as configurações de hardware recomendadas para servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede. A quantidade e as especificações recomendadas para os componentes do servidor também estão incluídas. Além disso, cada servidor é definido por site para fornecer uma representação completa dos requisitos do servidor por site.

- Requisitos de portas - Exibe um relatório de todas as portas habilitadas e a associação com DNS LB (balanceamento de carga DNS) e HLB (balanceadores de carga de hardware). Você deve usar esse relatório para planejar suas configurações de firewall e DNS LB e HLB.

- Relatório de Resumo - Exibe o resumo geral das configurações necessárias para configurar sua rede do Servidor de Borda.

- Relatório de Certificados - Exibe o nome da assunto e os nomes alternativos de assunto necessários para os certificados necessários para que os Servidores de Borda sejam executados.

- Relatório de firewall - Exibe as portas de origem e destino e endereços IP para interfaces externas e internas.

- Relatório dns - exibe o nome de domínio totalmente qualificado (FQDN) e endereços IP/VIP necessários para cada entrada DNS que você criar.

### <a name="microsoft-visio"></a>Microsoft Visio

Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:

> [!NOTE]
> Se o seu design for grande o suficiente para exigir mais de três Servidores Front-End, uma página adicional será criada para o pool de Front-End, Servidores #A0, o computador que executa o SQL Server, endereços IP e FQDNs.

- Topologia Global - Diagrama de sites configurados do Skype for Business Server 2015.

- Guia Nome do Site - Exibe a topologia de configuração do site com o Servidor de Borda, firewall, PSTN (rede telefônica pública comutado) com gateways e a implantação do servidor interno. A implantação interna consiste em servidores e pools configurados, incluindo os pools #A0, servidores baseados no SQL Server, Serviços de Domínio do Active Directory, Diretores, servidores de Unificação de Mensagens (UM) do Exchange, Servidores de Caixa de Correio do Exchange, Servidores do Office Web Apps, Servidores de Mediação e Servidores de Chat Persistente.

- Diagrama de Rede de Borda - Diagrama detalhando a configuração do Servidor de Borda com endereços IP e FQDNs associados. Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos. Além disso, diretores e o servidor de front-end ou pool de front-end são exibidos, com DNS LB ou HLB associado e o endereço IP atribuído (a Ferramenta de Planejamento suporta endereços IPv4 e IPv6) e FQDN.

## <a name="see-also"></a>Confira também
<a name="Optional_Software"> </a>

[Instalando a ferramenta de planejamento](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
