Launch Geoserver with NetCDF input and output support
docker run --name geoserver -d -p 8080:8080 --env INSTALL_EXTENSIONS=true --env STABLE_EXTENSIONS="netcdf,netcdf-out" --mount src="/home/vagrant/geoserver_data",target=/opt/geoserver_data/,type=bind docker.osgeo.org/geoserver:2.25.1

Launch PostGIS to support Image Mosaic datastore
docker run -d --name postgis -p 5432:5432 -e POSTGRES_USER=ccmm -e POSTGRES_PASSWORD=ccmm2024 -e POSTGRES_DB=ccmm -e PGDATA=/var/lib/postgresql/data/pgdata  -v ./data:/var/lib/postgresql/data --restart=always postgis/postgis
