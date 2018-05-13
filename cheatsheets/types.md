# Datatypes

**!! Work In Progress !!**

This sheet is unfinished, some types are missing!

## Numeric Types

### Integer Types

<table>
    <tr>
        <th>MySQL</th>
        <th>PostgreSQL</th>
        <th>Size (bytes)</th>
    </tr>
    <tr>
        <td>TINYINT</td>
        <td>/</td>
        <td>1</td>
    </tr>
    <tr>
        <td>SMALLINT</td>
        <td>SMALLINT</td>
        <td>2</td>
    </tr>
    <tr>
        <td>MEDIUMINT</td>
        <td>/</td>
        <td>3 on disk, 4 in memory</td>
    </tr>
    <tr>
        <td>INT / INTEGER</td>
        <td>INTEGER</td>
        <td>4</td>
    </tr>
    <tr>
        <td>BIGINT</td>
        <td>BIGINT</td>
        <td>8</td>
    </tr>
</table>

Modifiers only available in MySQL:
* UNSIGNED
* ZEROFILL

### Real Types

<table>
    <tr>
        <th>MySQL</th>
        <th>Size in MySQL (digits)</th>
        <th>PostgreSQL</th>
        <th>Size in PostgreSQL (digits)</th>
    </tr>
    <tr>
        <td>FLOAT</td>
        <td>53</td>
        <td>/</td>
        <td>/</td>
    </tr>
    <tr>
        <td>REAL</td>
        <td>Synonym for FLOAT or DOUBLE (depending on SQL_MODE)</td>
        <td>REAL</td>
        <td>6 decimals</td>
    </tr>
    <tr>
        <td>DOUBLE / DOUBLE PRECISION</td>
        <td>8 bytes</td>
        <td>DOUBLE PRECISION</td>
        <td>15 decimals</td>
    </tr>
    <tr>
        <td>DECIMAL / NUMERIC</td>
        <td>?</td>
        <td>
            DECIMAL / NUMERIC<br>
            MONEY
        </td>
        <td>
            integer part: 131072; decimal part: 16383<br>
            -92233720368547758.08 to +92233720368547758.07
        </td>
    </tr>
</table>

Modifiers only available in MySQL:
* UNSIGNED

### Serial Types

<table>
    <tr>
        <th>MySQL</th>
        <th>PostgreSQL</th>
        <th>Size (bytes)</th>
    </tr>
    <tr>
        <td>TINYINT AUTO_INCREMENT</td>
        <td>/</td>
        <td>1</td>
    </tr>
    <tr>
        <td>SMALLINT AUTO_INCREMENT</td>
        <td>SMALLSERIAL</td>
        <td>2</td>
    </tr>
    <tr>
        <td>MEDIUMINT AUTO_INCREMENT</td>
        <td>/</td>
        <td>3</td>
    </tr>
    <tr>
        <td>INT AUTO_INCREMENT</td>
        <td>SERIAL</td>
        <td>4</td>
    </tr>
    <tr>
        <td>BIGINT AUTO_INCREMENT</td>
        <td>BIGSERIAL</td>
        <td>8</td>
    </tr>
</table>

PostgreSQL alternative:

```
CREATE SEQUENCE tablename_colname_seq;
CREATE TABLE tablename (
    colname integer NOT NULL DEFAULT nextval('tablename_colname_seq')
);
ALTER SEQUENCE tablename_colname_seq OWNED BY tablename.colname;
```

PostgreSQL *obsolete* alternative:

```
CREATE TABLE t (...) WITH OIDS;
-- or omit WITH OIDS but first run:
SET default_with_oids = 1;

SELECT oid FROM t;
```

## String Types

### Character Types

<table>
    <tr>
        <th>MySQL</th>
        <th>Size in MySQL (characters)</th>
        <th>PostgreSQL</th>
        <th>Size in PostgreSQL (characters)</th>
    </tr>
    <tr>
        <td>CHAR</td>
        <td>Length specified at creation time; max: 65,535 or max row size</td>
        <td>CHAR / CHARACTER</td>
        <td>Length specified at creation time; no limit</td>
    </tr>
    <tr>
        <td>VARCHAR</td>
        <td>Length specified at creation time; max: 65,535 or max row size</td>
        <td>VARCHAR / CHARACTER VARYING</td>
        <td>Length specified at creation time; no limit</td>
    </tr>
    <tr>
        <td>
            TINYTEXT<br>
            TEXT<br>
            MEDIUMTEXT<br>
            LONGTEXT
        </td>
        <td>
            255B<br>
            64K<br>
            16M<br>
            4G
        </td>
        <td>TEXT</td>
        <td>No limit</td>
    </tr>
</table>

Modifiers only available in MySQL:
* CHARACTER SET
* COLLATION

### Binary Types

<table>
    <tr>
        <th>MySQL</th>
        <th>Size in MySQL</th>
        <th>PostgreSQL</th>
        <th>Size in PostgreSQL</th>
    </tr>
    <tr>
        <td>BIT</td>
        <td>Length specified at creation time; max: 64</td>
        <td>BIT</td>
        <td>Length specified at creation time; no limit; multiples of 8</td>
    </tr>
    <tr>
        <td>
            BINARY<br>
            VARBINARY
        </td>
        <td>
            See CHAR and VARCHAR
        </td>
        <td> </td>
        <td> </td>
    </tr>
    <tr>
        <td>
            TINYBLOB<br>
            BLOB<br>
            MEDIUMBLOB<br>
            LONGBLOB
        </td>
        <td>
            255B<br>
            64K<br>
            16M<br>
            4G
        </td>
        <td>
            BYTEA<br>
            BLOB
        </td>
        <td>
            1G<br>
            4T
        </td>
    </tr>
</table>

## Other

### Truth values

MySQL has the following aliases:

<table>
    <tr>
        <th>Alias</th>
        <th>Maps to</th>
    </tr>
    <tr>
        <td>BOOL / BOOLEAN</td>
        <td>TINYINT UNSIGNED</td>
    </tr>
    <tr>
        <td>TRUE</td>
        <td>1</td>
    </tr>
    <tr>
        <td>FALSE</td>
        <td>0</td>
    </tr>
    <tr>
        <td>
            IS TRUE<br>
            IS NOT TRUE
        </td>
        <td>
            = 1<br>
            != 1
        </td>
    </tr>
    <tr>
        <td>
            IS FALSE<br>
            IS NOT FALSE
        </td>
        <td>
            = 0, = ''<br>
            != 0, != ''
        </td>
    </tr>
    <tr>
        <td>IS [NOT] UNKNOWN</td>
        <td>IS [NOT] NULL</td>
    </tr>
</table>
