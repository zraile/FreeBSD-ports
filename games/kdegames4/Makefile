# $FreeBSD$

PORTNAME=	kdegames
PORTVERSION=	${KDE4_VERSION}
PORTREVISION=	1
CATEGORIES=	games kde

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Games for KDE 4 (meta port)

USES=		kde:4 metaport

OPTIONS_DEFINE=	ALL ${KDE4_GAMES_ALL}
OPTIONS_DEFAULT=	ALL

.include <${.CURDIR}/Makefile.common>

.for game in ${KDE4_GAMES_ALL}
# _PORT, _DETECT, and _DESC are defined in Makefile.common
${game}_PORT?=		games/${game}
${game}_DETECT?=	${KDE_PREFIX}/bin/${game}
${game}_DESC?=		Please fix a typo in option name/desc!
${game}_RUN_DEPENDS=	${${game}_DETECT}:${${game}_PORT}
ALL_RUN_DEPENDS+=	${${game}_RUN_DEPENDS}
.endfor

.include <bsd.port.mk>
