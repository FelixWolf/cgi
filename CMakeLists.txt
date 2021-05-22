# Distributed under the Boost Software License, Version 1.0.
# See http://www.boost.org/LICENSE_1_0.txt
# -*- cmake -*-

project(
    BoostCGI
    VERSION 0.1
    LANGUAGES CXX
)
set(CMAKE_CXX_STANDARD 11)
set(BoostCGI_USED_CXX_FEATURES cxx_auto_type)

find_package(Boost COMPONENTS filesystem thread iostreams date_time system unit_test_framework REQUIRED)

set(BoostCGI_SOURCE_FILES
)

set(BoostCGI_HEADER_FILES
    boost/cgi.hpp
    boost/cgi/fcgi.hpp
    boost/cgi/http/status_code.hpp
    boost/cgi/connections/tcp_socket.hpp
    boost/cgi/connections/stdio.hpp
    boost/cgi/connections/shareable_tcp_socket.hpp
    boost/cgi/connections/anonymous_pipe.hpp
    boost/cgi/connections/async_stdio.hpp
    boost/cgi/fcgi/transport_selection.hpp
    boost/cgi/fcgi/response.hpp
    boost/cgi/fcgi/request.hpp
    boost/cgi/fcgi/service.hpp
    boost/cgi/fcgi/acceptor.hpp
    boost/cgi/fcgi/client.hpp
    boost/cgi/fcgi/request_fwd.hpp
    boost/cgi/fcgi/fcgi_connection.hpp
    boost/cgi/fcgi/win32_acceptor_service_impl.hpp
    boost/cgi/fcgi/traits.hpp
    boost/cgi/fcgi/error.hpp
    boost/cgi/fcgi/request_acceptor_service.hpp
    boost/cgi/fcgi/acceptor_service_impl.hpp
    boost/cgi/fcgi/specification.hpp
    boost/cgi/fcgi/request_service.hpp
    boost/cgi/scgi/request.hpp
    boost/cgi/scgi/service.hpp
    boost/cgi/scgi/acceptor.hpp
    boost/cgi/scgi/request_parser.hpp
    boost/cgi/scgi/client.hpp
    boost/cgi/scgi/request_impl.hpp
    boost/cgi/scgi/traits.hpp
    boost/cgi/scgi/error.hpp
    boost/cgi/scgi/request_acceptor_service.hpp
    boost/cgi/scgi/request_service.hpp
    boost/cgi/basic_request.hpp
    boost/cgi/common/connection_base.hpp
    boost/cgi/common/source_enums.hpp
    boost/cgi/common/request_data.hpp
    boost/cgi/common/cookie.hpp
    boost/cgi/common/has_hidden_io_service.hpp
    boost/cgi/common/response.hpp
    boost/cgi/common/request_base.hpp
    boost/cgi/common/map.hpp
    boost/cgi/common/path_info.hpp
    boost/cgi/common/is_async.hpp
    boost/cgi/common/protocol_traits.hpp
    boost/cgi/common/parse_options.hpp
    boost/cgi/common/error.hpp
    boost/cgi/common/name.hpp
    boost/cgi/common/form_part.hpp
    boost/cgi/common/request_acceptor_service.hpp
    boost/cgi/common/header.hpp
    boost/cgi/common/tags.hpp
    boost/cgi/common/role_type.hpp
    boost/cgi/common/commit.hpp
    boost/cgi/common/io_service_provider.hpp
    boost/cgi/common/request_status.hpp
    boost/cgi/common/data_map_proxy.hpp
    boost/cgi/common/request_service.hpp
    boost/cgi/common/basic_protocol_service.hpp
    boost/cgi/common/form_parser.hpp
    boost/cgi/utility/stencil.hpp
    boost/cgi/utility/redirect.hpp
    boost/cgi/utility/sessions.hpp
    boost/cgi/basic_client.hpp
    boost/cgi/import/read.hpp
    boost/cgi/import/streambuf.hpp
    boost/cgi/import/io_service.hpp
    boost/cgi/import/basic_io_object.hpp
    boost/cgi/import/write.hpp
    boost/cgi/import/buffer.hpp
    boost/cgi/fwd/basic_client_fwd.hpp
    boost/cgi/fwd/basic_request_acceptor_fwd.hpp
    boost/cgi/fwd/data_map_proxy_fwd.hpp
    boost/cgi/fwd/basic_request_fwd.hpp
    boost/cgi/fwd/basic_connection_fwd.hpp
    boost/cgi/fwd/basic_protocol_service_fwd.hpp
    boost/cgi/fwd/io_service_provider_fwd.hpp
    boost/cgi/fwd/sessions_fwd.hpp
    boost/cgi/fwd/form_parser_fwd.hpp
    boost/cgi/fwd/request_service_fwd.hpp
    boost/cgi/error.hpp
    boost/cgi/cgi.hpp
    boost/cgi/scgi.hpp
    boost/cgi/basic_connection.hpp
    boost/cgi/config.hpp
    boost/cgi/detail/common_headers.hpp
    boost/cgi/detail/yield.hpp
    boost/cgi/detail/extract_params.hpp
    boost/cgi/detail/pop_options.hpp
    boost/cgi/detail/service_base.hpp
    boost/cgi/detail/basic_io_object.hpp
    boost/cgi/detail/url_decode.hpp
    boost/cgi/detail/throw_error.hpp
    boost/cgi/detail/service_id.hpp
    boost/cgi/detail/unyield.hpp
    boost/cgi/detail/save_environment.hpp
    boost/cgi/detail/basic_sync_io_object.hpp
    boost/cgi/detail/is_multimap.hpp
    boost/cgi/detail/push_options.hpp
    boost/cgi/detail/coroutine.hpp
    boost/cgi/cgi/request.hpp
    boost/cgi/cgi/service.hpp
    boost/cgi/cgi/acceptor.hpp
    boost/cgi/cgi/client.hpp
    boost/cgi/cgi/traits.hpp
    boost/cgi/cgi/request_service.hpp
    boost/cgi/basic_request_acceptor.hpp
)

set_source_files_properties(${BoostCGI_HEADER_FILES}
                            PROPERTIES HEADER_FILE_ONLY TRUE)

list(APPEND BoostCGI_SOURCE_FILES ${BoostCGI_HEADER_FILES})

add_library(BoostCGI STATIC ${BoostCGI_SOURCE_FILES})
TARGET_LINK_LIBRARIES(BoostCGI LINK_PUBLIC ${Boost_LIBRARIES})
set_target_properties(BoostCGI PROPERTIES LINKER_LANGUAGE CXX)
